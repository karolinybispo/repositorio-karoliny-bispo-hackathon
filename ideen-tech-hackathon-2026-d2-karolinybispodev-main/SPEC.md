# SPEC — Sistema de Reserva de Salas

## Histórias de usuário

- US-01: Como funcionário, quero reservar uma sala informando meu nome, a sala, a data e o horário, para garantir que ela estará disponível quando eu precisar.
- US-02: Como funcionário, quero ser avisado imediatamente se a sala já estiver ocupada no horário que escolhi, para evitar conflito.
- US-03: Como funcionário, quero que a Sala D nunca aceite reservas maiores que 1 hora, pois ela é destinada a reuniões rápidas.
- US-04: Como funcionário, quero ver todas as reservas de um dia específico, para planejar meu uso das salas.
- US-05: Como funcionário, quero cancelar uma reserva que eu fiz, para liberar a sala caso não precise mais.

## Contrato de interfaces

Não há API REST — o sistema é 100% client-side. A interface de dados é o `localStorage` do navegador.

### Modelo de dados (localStorage: chave `reservas`)

Array JSON de objetos de reserva:

| Campo         | Tipo   | Obrigatório | Descrição                          |
|---------------|--------|-------------|-------------------------------------|
| id            | string | sim         | UUID gerado no momento da criação  |
| responsavel   | string | sim         | Nome de quem fez a reserva          |
| sala          | string | sim         | "A", "B", "C" ou "D"               |
| data          | string | sim         | Formato ISO: YYYY-MM-DD            |
| inicio        | string | sim         | Horário de início: HH:MM           |
| fim           | string | sim         | Horário de término: HH:MM          |

### Salas e capacidades (constante no código)

| Sala | Capacidade | Restrição             |
|------|------------|-----------------------|
| A    | 10 pessoas | Nenhuma               |
| B    | 6 pessoas  | Nenhuma               |
| C    | 4 pessoas  | Nenhuma               |
| D    | 2 pessoas  | Máximo 1 hora por reserva |

## Critérios de aceitação por história

- US-01: Preencher todos os campos e clicar em "Reservar" cria a reserva e exibe confirmação.
- US-02: Ao submeter uma reserva conflitante, o sistema exibe mensagem de erro sem criar a reserva.
- US-03: Ao submeter reserva na Sala D com duração > 60 min, o sistema exibe mensagem de erro específica.
- US-04: Ao selecionar uma data no filtro de consulta, a lista exibe apenas as reservas daquela data, ordenadas por sala e horário.
- US-05: Clicar em "Cancelar" ao lado de uma reserva exibe confirmação e, após confirmação do usuário, remove a reserva permanentemente.

## Tecnologia escolhida

**HTML + CSS + JavaScript em arquivo único** — abre direto no navegador com dois cliques, sem instalar nada. Os dados ficam salvos no próprio navegador do computador (localStorage).

## UX / Fluxo principal

```
┌──────────────────────────────────────────────────────┐
│  🏢 Sistema de Reserva de Salas                      │
│──────────────────────────────────────────────────────│
│  [ Aba: Nova Reserva ]  [ Aba: Consultar por Dia ]   │
│──────────────────────────────────────────────────────│
│  ABA NOVA RESERVA:                                   │
│  Nome: [_________________________]                   │
│  Sala: [ A (10p) ▼ ]                                 │
│  Data: [ 2026-01-15 ]                                │
│  Início: [ 09:00 ]   Fim: [ 10:00 ]                  │
│  [ Reservar ]                                        │
│                                                      │
│  ABA CONSULTAR:                                      │
│  Data: [ 2026-01-15 ]  [ Ver Reservas ]              │
│                                                      │
│  09:00–10:00  Sala A  — João Silva  [ Cancelar ]     │
│  14:00–15:30  Sala B  — Maria Lima  [ Cancelar ]     │
└──────────────────────────────────────────────────────┘
```
