# Como usar a Fábrica de Software

> Você não precisa saber programar. Não precisa conhecer nenhum termo técnico.
> Basta descrever o que você quer — e o agente cuida do resto.

---

## O que você precisa

- Um agente de IA com capacidade de escrever e executar código (exemplos: Claude Code, Cursor, GitHub Copilot Workspace, ou qualquer outro)
- Acesso aos arquivos deste repositório

---

## Como funciona

As instruções da Fábrica de Software estão em dois arquivos de texto simples:

- `skills/fabricante-de-software.md` — instrui o agente a conduzir todo o processo de desenvolvimento
- `skills/seguranca.md` — instrui o agente a revisar a segurança do sistema gerado

Você fornece esses arquivos como contexto para o seu agente e descreve o que quer. O agente segue as instruções automaticamente.

---

## Passo 1 — Forneça as instruções ao seu agente

Dependendo do agente que você usa, há formas diferentes de carregar as instruções:

**Via prompt ou contexto inicial:**
Cole o conteúdo de `skills/fabricante-de-software.md` no início da conversa com o agente, antes de descrever o que você quer.

**Via arquivo de contexto do projeto:**
Alguns agentes leem arquivos de instrução automaticamente quando você abre a pasta do projeto. Consulte a documentação do seu agente para saber como configurar isso.

---

## Passo 2 — Descreva o que você quer

Com as instruções carregadas, descreva sua necessidade em português simples.

**Exemplos:**

> "Quero um caderno de receitas digital com cadastro de ingredientes e modo de preparo."

> "Preciso de uma lista de tarefas para o dia a dia com opção de marcar como concluída."

> "Quero um sistema para controlar meu estoque com nome, quantidade e preço de cada produto."

Quanto mais você contar, melhor. Se faltar informação, o agente vai perguntar.

---

## Passo 3 — O agente gera o PRD

Antes de planejar, o agente escreve um `PRD.md` — um documento de uma página com o problema, o público, o objetivo e o escopo do que será desenvolvido.

---

## Passo 4 — Revise e aprove o plano

O agente gera um `SPEC.md` com as histórias de usuário e o contrato do sistema, e apresenta o plano completo:

- O que será desenvolvido
- Como vai funcionar
- Qual tecnologia será usada e por quê
- Quais testes serão feitos

**Leia com calma.** Se algo não estiver certo, diga — o agente ajusta.

Quando estiver satisfeito, escreva:

```
Aprovado, pode começar.
```

O desenvolvimento começa só depois dessa aprovação.

---

## Passo 5 — Acompanhe o desenvolvimento

O agente constrói o sistema e informa o progresso. Você não precisa fazer nada — apenas acompanhar. Se quiser mudar algo, é só dizer.

---

## Passo 6 — Veja os resultados dos testes

Quando o desenvolvimento terminar, o agente executa os testes e mostra os resultados:

```
✅ Cadastro funcionando — passou
✅ Busca por nome — passou
✅ Campo obrigatório vazio retorna aviso — passou
```

---

## Passo 7 — Revisão de segurança (automática)

Após os testes, o agente executa a revisão de segurança automaticamente seguindo `skills/seguranca.md` — você não precisa pedir. O relatório inclui:

- Problemas encontrados (do mais grave ao menos grave)
- Impacto de cada problema
- Correções aplicadas
- Parecer final: **Aprovado**, **Reprovado** ou **Aprovado com ressalvas**

---

## Passo 8 — Receba o sistema pronto

Com tudo aprovado, o agente entrega o sistema funcionando e explica como abrir e usar.

> Para projetos simples, é um arquivo HTML que você abre com dois cliques no navegador — sem instalar nada.

---

## Dúvidas frequentes

**Preciso saber programar?**
Não. Descreva o que quer em palavras normais.

**Funciona com qualquer agente de IA?**
Sim. As skills são arquivos de texto com instruções em linguagem natural. Qualquer agente que consiga ler e seguir instruções em markdown consegue executar o fluxo.

**E se eu não gostar do plano?**
Diga o que quer mudar. O agente ajusta e apresenta novamente.

**O agente pode errar?**
Sim — como qualquer desenvolvedor. Por isso existem os testes e a revisão de segurança. Se algo não funcionar, informe e o agente corrige.

**O código gerado é meu?**
Sim. Tudo fica no seu computador, no seu repositório, sob seu controle.

---

## Resumo rápido

```
1. Carregue skills/fabricante-de-software.md como contexto do seu agente
2. Descreva o que você quer em português
3. Aguarde o PRD e o SPEC gerados automaticamente
4. Aprove o plano
5. Aguarde o desenvolvimento, os testes e a revisão de segurança
6. Receba o sistema pronto
```

---

> Feito para transformar qualquer ideia em software — independente do seu nível técnico ou do agente que você usa.
