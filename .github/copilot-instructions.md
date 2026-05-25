# GitHub Copilot Instructions

Use estas instruções como regra geral para respostas, sugestões e alterações neste repositório-base.

Este repositório serve como ponto de partida para novos projetos. Preserve a estrutura reutilizável e evite registrar aqui requisitos de um projeto específico, salvo quando o objetivo for ajustar o próprio toolkit.

## Fluxo SDD

- Use somente dois arquivos SDD: `docs/SDD-origin.md` e `docs/SDD-dev.md`.
- Não crie arquivos `SDD-*.template.md`; os dois SDDs ativos já são os modelos canônicos.
- Em tarefas de desenvolvimento, correção, refatoração, revisão, testes, interface, backend ou alteração de comportamento, use o fluxo do agente `sdd-specialist`.
- Trate `docs/SDD-origin.md` como fonte de verdade para requisitos, regras, fluxos, decisões validadas, permissões, entidades e limitações do projeto que usar esta base.
- Trate `docs/SDD-dev.md` como registro da implementação atual, contendo apenas o que foi realmente tratado, decidido e validado.
- Não invente requisitos, telas, APIs, fluxos, entidades ou regras de negócio.
- Não altere regra de negócio sem confirmação explícita.
- Se os arquivos SDD não existirem, sinalize a ausência e proponha criação mínima antes de registrar decisões.

## Edição

- Aplicar alterações em bloco único/consolidado sempre que possível.
- Alterar somente o necessário para atender à tarefa.
- Não reformatar arquivos inteiros sem necessidade.
- Não misturar correção, refatoração e nova funcionalidade sem solicitação.
- Preservar padrões, contratos, nomes, estrutura e comportamento existente.

## Código

- Priorizar código simples, legível, seguro e fácil de manter.
- Evitar overengineering.
- Não adicionar dependências externas sem solicitação.
- Tratar erros de forma explícita.
- Considerar casos de borda.
- Preservar contratos de APIs, funções, componentes e tipos existentes.

## Frontend

- Evitar CSS inline.
- Priorizar componentes reutilizáveis.
- Usar HTML semântico.
- Preservar acessibilidade, responsividade e foco visível.
- Validar estados de loading, erro, vazio, sucesso e disabled quando aplicável.

## Testes e Validação

- Criar ou ajustar testes quando fizer sentido para o comportamento alterado.
- Priorizar testes que validem comportamento, não detalhes internos.
- Informar claramente quando não for possível executar testes.
- Não afirmar que algo foi validado se não foi.

## Resposta Final

Ao concluir, responder com resumo curto contendo:

- O que foi alterado.
- Arquivos impactados.
- Validações realizadas.
- Validações pendentes, se houver.
- Atualização feita no SDD, quando aplicável.
