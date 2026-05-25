# AI Toolkit

Repositorio de estudo sobre SDD, skills e agentes de IA aplicados ao desenvolvimento de software.

O objetivo deste projeto e organizar uma base experimental para entender como documentar requisitos, orientar agentes, reutilizar skills e criar fluxos de trabalho mais rastreaveis com IA no ciclo de desenvolvimento.

## O que este repositorio contem

- Modelos de SDD para especificacao e registro incremental de implementacoes.
- Instrucoes gerais para agentes de IA atuarem com seguranca, clareza e rastreabilidade.
- Agentes especializados para revisao de codigo, frontend e testes.
- Agente SDD para orientar qualquer tarefa de desenvolvimento pelo fluxo `origin` e `dev`.
- Skills reutilizaveis para acessibilidade frontend, aprofundamento de requisitos e geracao/revisao de testes.
- Prompts auxiliares para manter a documentacao SDD atualizada.
- Regras basicas para uso com GitHub Copilot no contexto do projeto.

Este repositorio nao e uma aplicacao executavel. Ele funciona como material de estudo, referencia e ponto de partida para experimentos com IA aplicada ao desenvolvimento.

## Estrutura

```text
.
+-- AGENTS.md
+-- docs/
|   +-- SDD-origin.md
|   +-- SDD-dev.md
+-- .github/
    +-- copilot-instructions.md
    +-- agents/
    |   +-- code-reviewer.agent.md
    |   +-- frontend-specialist.agent.md
    |   +-- sdd-specialist.agent.md
    |   +-- test-engineer.agent.md
    +-- prompts/
    |   +-- atualizar-sdd.prompt.md
    +-- skills/
        +-- frontend-accessibility/
        |   +-- SKILL.md
        +-- requirement-discovery/
        |   +-- SKILL.md
        +-- test-generation/
            +-- SKILL.md
```

## Documentos principais

### `AGENTS.md`

Define orientacoes gerais para agentes de IA, incluindo escopo de alteracao, forma de edicao, cuidados com codigo, testes, documentacao, frontend, backend, seguranca e uso de ferramentas externas.

Este arquivo funciona como a politica geral de colaboracao dos agentes dentro do repositorio.

### `docs/SDD-origin.md`

Modelo base para especificacao do sistema. Deve ser usado para registrar requisitos, contexto, escopo, usuarios, fluxos, dados, integracoes, permissoes, estados de interface, riscos e pendencias.

Ele representa a especificacao mais ampla do produto, modulo ou sistema em estudo.

### `docs/SDD-dev.md`

Modelo para registro incremental de implementacoes. Deve ser atualizado a cada tarefa para documentar somente o que foi realmente tratado: objetivo, escopo, impactos, arquivos alterados, decisoes, validacoes, riscos e pendencias.

Ele ajuda a manter rastreabilidade entre pedido, implementacao e validacao.

## Agentes

### `sdd-specialist`

Agente responsavel por manter o fluxo SDD em qualquer tarefa de desenvolvimento. Deve ser usado em prompts que envolvam criacao, correcao, refatoracao, interface, backend, testes, revisao tecnica ou alteracao de comportamento.

Ele usa `docs/SDD-origin.md` como fonte de verdade do produto ou modulo e `docs/SDD-dev.md` como registro do escopo realmente tratado em cada implementacao.

### `code-reviewer`

Agente voltado para revisao tecnica, arquitetura, organizacao, clareza, uso de IA, MCP, plugins, skills e escalabilidade do estudo.

Seu foco nao e apenas encontrar erros, mas tambem explicar impactos, ensinar boas praticas e sugerir melhorias proporcionais ao contexto experimental.

### `frontend-specialist`

Agente especializado em transformar requisitos do SDD em interfaces frontend organizadas, acessiveis, responsivas e componentizadas.

Tambem orienta o uso de Figma/MCP e a combinacao entre codigo deterministico e codigo gerado por IA.

### `test-engineer`

Agente focado em validar se a implementacao segue a especificacao. Atua sobre testes funcionais, visuais, acessibilidade, qualidade tecnica e riscos de regressao.

Seu criterio central e SDD-first: uma feature so deve ser considerada pronta quando atende a especificacao e possui comportamento previsivel.

## Skills

### `frontend-accessibility`

Skill para orientar criacao, revisao e validacao de interfaces com foco em acessibilidade, semantica HTML, teclado, foco, formularios, contraste, ARIA, modais, tabelas, imagens e responsividade.

### `requirement-discovery`

Skill para aprofundar uma historia, ideia ou requisito incompleto antes da implementacao. Ajuda a definir escopo, regras, criterios de aceite, lacunas e testes necessarios para comprovar que o requisito foi atendido.

### `test-generation`

Skill para orientar criacao, revisao e ampliacao de testes automatizados. Prioriza testes de comportamento, cenarios positivos, negativos, casos de borda, mocks e prevencao de regressao.

## Prompts e instrucoes auxiliares

### `.github/prompts/atualizar-sdd.prompt.md`

Prompt de apoio para atualizar os documentos SDD sem remover requisitos anteriores, mantendo historico funcional e alterando apenas o necessario.

### `.github/copilot-instructions.md`

Instrucoes curtas para o Copilot no repositorio, com foco em evitar CSS inline e priorizar componentes reutilizaveis.

## Fluxo de estudo sugerido

1. Definir ou revisar a especificacao em `docs/SDD-origin.md`.
2. Registrar a implementacao planejada ou realizada em `docs/SDD-dev.md`.
3. Usar `sdd-specialist` como agente base para delimitar requisito, escopo, criterio de aceite e validacoes.
4. Quando o pedido ainda estiver vago, aplicar a skill `requirement-discovery`.
5. Selecionar o agente executor mais adequado para a tarefa:
   - `frontend-specialist` para interface.
   - `test-engineer` para validacao e testes.
   - `code-reviewer` para revisao e melhoria estrutural.
6. Usar skills aplicaveis como referencia tecnica.
7. Atualizar os SDDs ao final da tarefa com escopo real, decisoes e validacoes.
8. Revisar se o resultado preserva clareza, seguranca, rastreabilidade e manutencao.

## Principios do repositorio

- SDD como fonte de verdade.
- `SDD-origin.md` para requisitos e decisoes validadas.
- `SDD-dev.md` para registro da implementacao atual.
- Alteracoes pequenas, seguras e rastreaveis.
- Agentes com responsabilidades claras.
- Skills como guias reutilizaveis, nao como substitutas da analise do contexto.
- Preservacao de funcionalidades e regras de negocio.
- Documentacao objetiva do que foi realmente implementado ou validado.
- Uso de IA como apoio tecnico, nao como substituto da revisao humana.

## Limitacoes atuais

- Nao ha codigo de aplicacao neste repositorio.
- Nao ha suite de testes automatizados para executar.
- Os arquivos sao modelos e instrucoes, portanto a validacao principal e documental.
- O conteudo ainda pode evoluir com exemplos praticos, casos de uso e fluxos reais de aplicacao.

## Publico-alvo

Este repositorio e indicado para desenvolvedores que querem estudar:

- Spec Driven Development.
- Organizacao de agentes de IA.
- Criacao e uso de skills.
- Fluxos com GitHub Copilot, Codex, MCP e Figma MCP.
- Documentacao tecnica orientada a rastreabilidade.
- Integracao entre IA generativa e boas praticas de engenharia.
