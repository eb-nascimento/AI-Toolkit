---
name: requirement-discovery
description: Use esta skill ao receber uma historia, ideia, pedido de funcionalidade ou requisito incompleto que precise ser aprofundado antes da implementacao, definindo escopo, criterios de aceite, impactos no SDD e testes necessarios para considerar o requisito atendido.
---

# Requirement Discovery

Use esta skill para transformar uma historia, ideia ou pedido inicial em requisito claro, verificavel e pronto para orientar implementacao.

Ela deve ser usada antes de implementar quando a solicitacao ainda estiver vaga, incompleta, sem criterio de aceite ou sem testes esperados.

## Objetivo

Ajudar a definir o requisito no SDD a partir de uma historia ou necessidade, conectando:

- problema;
- usuario ou ator;
- objetivo;
- regra de negocio;
- escopo;
- criterios de aceite;
- estados de interface, quando houver;
- validacoes e testes necessarios.

## Entradas esperadas

Quando possivel, colete ou inferira com cuidado:

- historia ou pedido original;
- usuario impactado;
- problema a resolver;
- resultado esperado;
- restricoes conhecidas;
- fluxos principais;
- fluxos alternativos;
- casos de erro;
- dados envolvidos;
- dependencias externas;
- riscos ou premissas.

Quando a informacao nao existir, registre como lacuna ou pergunta. Nao invente requisito como se fosse validado.

## Processo recomendado

1. Reescrever a historia em linguagem objetiva.
2. Identificar o objetivo do usuario e o valor esperado.
3. Separar requisito funcional de requisito nao funcional.
4. Definir o que esta dentro e fora do escopo.
5. Mapear regras, restricoes e excecoes.
6. Definir criterios de aceite verificaveis.
7. Derivar testes que comprovem atendimento do requisito.
8. Indicar onde registrar a informacao no SDD.

## Checklist de aprofundamento

### Contexto

- Qual problema esta sendo resolvido?
- Quem e impactado?
- Por que isso e necessario agora?
- Existe comportamento anterior que deve ser preservado?

### Escopo

- O que deve ser entregue?
- O que explicitamente nao sera entregue?
- Existe mudanca de regra de negocio?
- Existe impacto em dados, integracoes, permissao ou interface?

### Comportamento esperado

- Qual e o fluxo principal?
- Quais sao os fluxos alternativos?
- O que acontece em erro?
- O que acontece em estado vazio?
- O que acontece com dados invalidos?
- O que acontece com permissao insuficiente?

### Criterios de aceite

Cada criterio deve ser observavel e testavel.

Preferir formato:

```text
Dado [contexto], quando [acao], entao [resultado esperado].
```

Evitar criterios vagos como:

- "deve funcionar bem";
- "deve ser intuitivo";
- "deve ser rapido";
- "deve melhorar a experiencia".

Quando houver requisito nao funcional, transforme em criterio mensuravel ou verificavel.

### Testes necessarios

Para considerar o requisito atendido, definir:

- teste do fluxo principal;
- teste de validacao ou entrada invalida;
- teste de estado vazio, erro ou permissao, quando aplicavel;
- teste de regressao se houver comportamento existente;
- teste de acessibilidade se houver interface;
- validacao manual quando nao houver automacao disponivel.

## Saida esperada

Ao aplicar esta skill, produza:

## Requisito refinado

Descricao objetiva do requisito.

## Escopo

- Dentro:
- Fora:

## Regras e premissas

- Regras validadas:
- Premissas:
- Lacunas:

## Criterios de aceite

- Dado ..., quando ..., entao ...

## Testes para aprovacao

- Cenario:
- Tipo de teste:
- Resultado esperado:

## Atualizacao no SDD

- `docs/SDD-origin.md`: informacoes que representam regra ou requisito validado.
- `docs/SDD-dev.md`: informacoes da implementacao atual, validacoes e decisoes tomadas.

## Regras

- Nao implementar antes de entender o requisito minimo.
- Nao transformar suposicao em requisito validado.
- Nao remover requisito anterior sem justificativa.
- Nao definir teste apenas para detalhe interno.
- Priorizar comportamento observavel pelo usuario ou pelo contrato da API.
- Registrar lacunas de forma explicita.
