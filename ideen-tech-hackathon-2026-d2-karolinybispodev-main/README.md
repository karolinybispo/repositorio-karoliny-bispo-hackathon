# Fábrica de Software — Agente de IA com Skills Especializadas

> Ideen Tech Hackathon 2026 · Desafio 2 · Karoliny Bispo Dev

---

## 1. O problema

Realizar a construção de uma skiLl que faça qualquer agente de IA construir um sistema de software. 

---

## 2. O que foi feito

Um pacote de duas skills escritas em markdown que instrui qualquer agente de IA a percorrer as quatro etapas obrigatórias:

### Skills incluídas

Os arquivos em `skills/` são markdown puro — podem ser usados com qualquer agente de IA como prompt de sistema ou contexto de sessão.

- **`skills/fabricante-de-software.md`** — skill principal. Instrui o agente a assumir os papéis de Product Owner, UX Designer, Desenvolvedor, QA e Engenheiro de Testes. Ao concluir os testes, aciona a revisão de segurança automaticamente.
- **`skills/seguranca.md`** — skill independente de revisão de segurança baseada em OWASP Top 10, OWASP ASVS, NIST SSDF e CWE Top 25.

### Como com agente

Cole o conteúdo de `skills/fabricante-de-software.md` como prompt de sistema ou contexto inicial da sessão. O agente vai seguir o fluxo das quatro etapas a partir do pedido em linguagem natural.

---

### Execução com o pedido de treino

Com a IA aberta e possuindo o contexto da skill, escreva o que ela deve fazer ou a instrua a ler um documento que contenha o pedido do sistema a ser desenvolvido.
Por exemplo:

> "leia o PEDIDO-TREINO.md"

O agente carrega as instruções das skills e executa o fluxo completo


### Onde o agente errou:

Eu iniciei o projeto seguindo uma linha, conforme eu ia avançando e relendo os critérios, fui alterando o sistema final com auxílio da IA. Eu informava a ela o que devia fazer e com isso ela construia. Isso ajudou no quisito agilidade, pois se eu fosse fazer na mão, causaria tempo gasto desnecessário. Portanto, no primeiro teste, antes da finalização desse projeto, ela criou a pasta evidência, porém nesse último teste final, ela não criou. A pasta evidência foi criado manualmente por mim.

---

