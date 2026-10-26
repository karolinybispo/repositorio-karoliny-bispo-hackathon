# PRD — Sistema de Reserva de Salas

## Problema
Funcionários do escritório não têm um meio centralizado de reservar salas de reunião, o que gera conflitos de agendamento e uso simultâneo indevido.

## Público-alvo
Funcionários em geral, qualquer nível técnico, usando computadores com navegador web (Chrome, Edge, Firefox). Não é exigido conhecimento técnico para operar o sistema.

## Objetivo
Qualquer funcionário consegue reservar uma sala em menos de 1 minuto, visualizar as reservas do dia e cancelar quando necessário — sem conflito de horários e sem precisar instalar nada.

## Escopo desta versão

### Dentro
- Formulário de reserva: nome do responsável, sala, data, horário de início e fim
- Validação de conflito: impede reserva dupla na mesma sala e horário
- Regra especial da Sala D: máximo 1 hora por reserva
- Listagem de reservas por dia
- Cancelamento de reserva

### Fora
- Login ou autenticação de usuários
- Notificações por e-mail ou mensagem
- Painel administrativo
- Relatórios ou histórico

## Restrições
- Nenhuma instalação de software pelo usuário
- Roda localmente no navegador (arquivo HTML único)
- Sem dependência de servidor ou banco de dados externo
- Idioma: Português

## Critérios de aceitação
- [ ] É possível fazer uma reserva preenchendo nome, sala, data e horário
- [ ] O sistema impede reserva de sala já ocupada no período solicitado
- [ ] A Sala D não aceita reservas com duração superior a 1 hora
- [ ] É possível listar todas as reservas de um dia específico
- [ ] É possível cancelar uma reserva existente
- [ ] O sistema abre com dois cliques no arquivo, sem instalação
- [ ] As reservas persistem entre atualizações de página (armazenadas no navegador)
