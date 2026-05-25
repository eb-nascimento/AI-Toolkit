# Instruções para Agentes de IA

Este repositório é uma base reutilizável para novos projetos com apoio de IA. Ele não é uma aplicação final; preserve a estrutura para que possa ser copiada, adaptada e usada em projetos futuros.

O objetivo é garantir que respostas, alterações de código, revisões e sugestões sejam úteis, seguras, rastreáveis e alinhadas ao fluxo SDD do projeto que estiver usando esta base.

---

## Princípios Gerais

- Atuar como apoio técnico ao desenvolvimento, não como substituto da análise humana.
- Priorizar clareza, segurança, manutenção, rastreabilidade e aprendizado.
- Evitar alterações desnecessárias ou fora do escopo solicitado.
- Preservar funcionalidades, contratos, testes, documentação e regras de negócio existentes.
- Não assumir requisitos não informados.
- Quando houver dúvida relevante, sinalizar antes de alterar.
- Para dúvidas pequenas, sem impacto em regra, contrato, dados, permissões ou fluxo crítico, registrar a premissa e seguir com a solução mais conservadora.
- Responder com objetividade e resumo curto ao final das alterações.

---

## Fluxo SDD Obrigatório

Toda tarefa de desenvolvimento, correção, refatoração, interface, backend, teste, revisão técnica ou alteração de comportamento deve considerar o fluxo SDD.

Este repositório mantém somente dois arquivos SDD canônicos:

- `docs/SDD-origin.md`: fonte de verdade para requisitos, regras, decisões validadas, fluxos, entidades, permissões e limitações do projeto real.
- `docs/SDD-dev.md`: registro da implementação atual, preenchido com o escopo realmente tratado, decisões, impactos, validações e pendências.

Regras:

- Não criar arquivos `SDD-*.template.md`; os dois arquivos SDD ativos já são os modelos base.
- Não registrar no SDD comportamento que não foi implementado ou validado.
- Não usar `SDD-origin.md` como changelog de implementação.
- Não usar `SDD-dev.md` para antecipar requisitos ainda não tratados.
- Se algum arquivo SDD não existir no projeto derivado, sinalizar a ausência e propor criação mínima antes de registrar decisões.
- Ao alterar este repositório-base, preservar os SDDs como modelos limpos, salvo solicitação explícita para registrar um exemplo preenchido.

---

## Escopo de Alteração

Antes de modificar qualquer arquivo:

- Entender o objetivo da tarefa.
- Identificar requisito, critério de aceite e validação esperada.
- Identificar arquivos relacionados.
- Evitar alterações amplas quando uma correção pontual resolver.
- Não editar arquivos fora do escopo sem necessidade.
- Não misturar refatoração com correção de bug, a menos que solicitado.
- Não criar novos padrões se o projeto já possuir um padrão estabelecido.

---

## Forma de Edição

- Aplicar alterações em blocos coesos, pequenos e revisáveis.
- Evitar múltiplas microalterações que dificultem revisão.
- Manter código e documentação legíveis, consistentes e alinhados ao estilo do projeto.
- Preservar nomes, contratos, estruturas e padrões já utilizados.
- Não reformatar arquivos inteiros sem necessidade.

---

## Código

Ao criar ou alterar código:

- Seguir a arquitetura e os padrões existentes.
- Priorizar soluções simples, compreensíveis e incrementais.
- Evitar overengineering.
- Não introduzir dependências externas sem solicitação.
- Tratar erros de forma clara.
- Considerar casos de borda.
- Evitar duplicação desnecessária.
- Manter compatibilidade com o comportamento atual.
- Preservar contratos de APIs, funções, componentes e tipos existentes.
- Não alterar regras de negócio sem solicitação explícita.

---

## Testes e Validações

Quando a tarefa envolver comportamento funcional:

- Verificar se já existem testes relacionados.
- Criar ou ajustar testes quando fizer sentido.
- Priorizar testes que validem comportamento, não detalhes internos.
- Considerar cenários positivos, negativos e casos de borda.
- Não remover testes existentes sem justificativa.
- Informar quando não for possível executar testes.
- Se a validação não puder ser executada, não declarar a tarefa como validada; registrar limitação, risco e teste pendente.

---

## Documentação

Quando a alteração impactar funcionamento, arquitetura, requisitos ou uso:

- Atualizar documentação relacionada.
- Manter documentação objetiva e coerente com o código.
- Não documentar comportamento que não foi implementado.
- Não remover histórico ou decisões importantes sem solicitação.
- Registrar limitações, premissas e pontos pendentes quando necessário.

---

## Frontend

Ao atuar em interfaces:

- Preservar acessibilidade, semântica HTML e navegação por teclado.
- Usar HTML nativo sempre que possível antes de ARIA.
- Manter foco visível.
- Evitar `div` ou `span` clicáveis sem papel acessível.
- Garantir labels em campos de formulário.
- Preservar responsividade existente.
- Não alterar layout visual de forma ampla sem solicitação.
- Validar estados de loading, erro, vazio, sucesso e disabled quando aplicável.

---

## Backend

Ao atuar em backend:

- Preservar contratos de entrada e saída.
- Validar dados recebidos.
- Tratar erros de forma explícita.
- Evitar expor dados sensíveis em logs ou respostas.
- Considerar autenticação, autorização e permissões.
- Evitar mudanças que quebrem integrações existentes.
- Manter consistência com padrões de rotas, services, repositories e middlewares do projeto.

---

## Segurança

- Não expor chaves, tokens, credenciais ou dados sensíveis.
- Não inserir segredos diretamente no código.
- Não enfraquecer autenticação, autorização ou validações.
- Não ignorar erros de segurança.
- Sinalizar riscos quando identificados.
- Usar variáveis de ambiente para configurações sensíveis.

---

## Uso de Agentes e Skills

- Use `sdd-specialist` para delimitar requisito, escopo, critérios de aceite, validações e atualização do SDD.
- Use `frontend-specialist` para interfaces, componentes, UX, responsividade e acessibilidade.
- Use `test-engineer` para testes, cenários, validações e riscos de regressão.
- Use `code-reviewer` para revisão técnica, arquitetura, segurança, regressão e qualidade.
- Use `frontend-accessibility` para revisão de acessibilidade em interfaces.
- Use `test-generation` para criação ou revisão de testes automatizados.
- Use `requirement-discovery` quando a solicitação estiver vaga ou incompleta.

A skill deve orientar a tarefa, mas não substituir a análise do contexto real do projeto.

---

## Uso de MCP e Ferramentas Externas

Quando houver MCP ou ferramenta externa disponível:

- Usar apenas quando agregar contexto relevante.
- Não assumir que o MCP é a IA; MCP é fonte de contexto ou ferramenta.
- Validar entradas necessárias antes de usar ferramentas externas.
- Informar quando uma ferramenta falhar ou não estiver disponível.
- Não simular sucesso quando a consulta externa não ocorreu.

---

## Resposta Esperada ao Concluir Tarefas

Ao concluir uma tarefa, responder preferencialmente com:

- Requisito tratado.
- Escopo realizado.
- Arquivos alterados.
- Critérios de aceite atendidos.
- Validações realizadas.
- Validações pendentes, se houver.
- Atualizações feitas em `SDD-dev.md`, quando aplicável.
- Atualizações feitas em `SDD-origin.md`, somente se aplicável.
- Riscos, premissas ou decisões que exigem validação humana.

---

## Restrições Importantes

- Não remover funcionalidades existentes sem solicitação explícita.
- Não alterar regra de negócio sem confirmação.
- Não adicionar dependências sem necessidade.
- Não aplicar refatorações amplas sem alinhamento.
- Não afirmar que algo foi testado se não foi.
- Não inventar arquivos, APIs, telas ou comportamentos.
- Não ocultar falhas, incertezas ou limitações.

---

## Preferências de Execução

- Alterar somente o necessário.
- Ser objetivo.
- Otimizar uso de tokens.
- Priorizar soluções seguras e incrementais.
- Manter rastreabilidade das decisões.
- Sinalizar riscos antes de propor mudanças maiores.
