# Instruções para Agentes de IA

Este arquivo define orientações gerais para agentes de IA utilizados no apoio ao desenvolvimento de software.

O objetivo é garantir que respostas, alterações de código, revisões e sugestões sejam úteis, seguras, rastreáveis e alinhadas às boas práticas da equipe.

## Princípios gerais

- Atuar como apoio técnico ao desenvolvimento, não como substituto da análise humana.
- Priorizar clareza, segurança, manutenção e rastreabilidade.
- Evitar alterações desnecessárias ou fora do escopo solicitado.
- Preservar funcionalidades existentes.
- Não remover código, testes, documentação ou regras de negócio sem justificativa clara.
- Não assumir requisitos não informados.
- Quando houver dúvida relevante, sinalizar antes de alterar.
- Responder com objetividade e resumo curto ao final das alterações.

## Escopo de alteração

Antes de modificar qualquer arquivo:

- Entender o objetivo da tarefa.
- Identificar os arquivos relacionados.
- Evitar alterações amplas quando uma correção pontual resolver.
- Não editar arquivos fora do escopo sem necessidade.
- Não misturar refatoração com correção de bug, a menos que solicitado.
- Não criar novos padrões se o projeto já possuir um padrão estabelecido.

## Forma de edição

- Não editar linha por linha quando a alteração puder ser aplicada de forma consolidada.
- Aplicar mudanças em bloco único ou em alterações coesas.
- Evitar múltiplas microalterações que dificultem revisão.
- Manter o código legível e consistente com o estilo do projeto.
- Preservar nomes, contratos, estruturas e padrões já utilizados.
- Não reformatar arquivos inteiros sem necessidade.

## Código

Ao criar ou alterar código:

- Seguir a arquitetura e os padrões existentes.
- Priorizar soluções simples e compreensíveis.
- Evitar overengineering.
- Não introduzir dependências externas sem solicitação.
- Tratar erros de forma clara.
- Considerar casos de borda.
- Evitar duplicação desnecessária.
- Manter compatibilidade com o comportamento atual.
- Preservar contratos de APIs, funções, componentes e tipos existentes.
- Não alterar regras de negócio sem solicitação explícita.

## Testes

Quando a tarefa envolver código funcional:

- Verificar se já existem testes relacionados.
- Criar ou ajustar testes quando fizer sentido.
- Priorizar testes que validem comportamento, não detalhes internos.
- Considerar cenários positivos, negativos e casos de borda.
- Não remover testes existentes sem justificativa.
- Informar quando não for possível executar testes.

## Documentação

Quando a alteração impactar funcionamento, arquitetura, requisitos ou uso:

- Atualizar documentação relacionada.
- Manter documentação objetiva e coerente com o código.
- Não documentar comportamento que não foi implementado.
- Não remover histórico ou decisões importantes sem solicitação.
- Registrar limitações, premissas e pontos pendentes quando necessário.

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

## Backend

Ao atuar em backend:

- Preservar contratos de entrada e saída.
- Validar dados recebidos.
- Tratar erros de forma explícita.
- Evitar expor dados sensíveis em logs ou respostas.
- Considerar autenticação, autorização e permissões.
- Evitar mudanças que quebrem integrações existentes.
- Manter consistência com padrões de rotas, services, repositories e middlewares do projeto.

## Segurança

- Não expor chaves, tokens, credenciais ou dados sensíveis.
- Não inserir segredos diretamente no código.
- Não enfraquecer autenticação, autorização ou validações.
- Não ignorar erros de segurança.
- Sinalizar riscos quando identificados.
- Usar variáveis de ambiente para configurações sensíveis.

## Git e revisão

Ao preparar alterações:

- Manter mudanças pequenas e revisáveis.
- Explicar o que foi alterado.
- Separar correção, refatoração e nova funcionalidade quando possível.
- Não criar commits ou PRs sem solicitação.
- Quando solicitado, sugerir mensagem de commit clara e objetiva.

## Uso de skills

Quando houver uma skill aplicável, utilizá-la como referência.

Exemplos:

- `frontend-accessibility`: para criação ou revisão de interfaces acessíveis.
- `test-generation`: para criação, revisão ou ampliação de testes automatizados.

A skill deve orientar a tarefa, mas não substituir a análise do contexto real do projeto.

## Uso de MCP e ferramentas externas

Quando houver MCP ou ferramenta externa disponível:

- Usar apenas quando agregar contexto relevante.
- Não assumir que o MCP é a IA; MCP é fonte de contexto ou ferramenta.
- Validar entradas necessárias antes de usar ferramentas externas.
- Informar quando uma ferramenta falhar ou não estiver disponível.
- Não simular sucesso quando a consulta externa não ocorreu.

## Resposta esperada ao concluir tarefas

Ao concluir uma tarefa, responder preferencialmente com:

- Resumo do que foi alterado.
- Validações realizadas.
- Observações, limitações, riscos ou próximos passos.

## Restrições importantes

- Não remover funcionalidades existentes sem solicitação explícita.
- Não alterar regra de negócio sem confirmação.
- Não adicionar dependências sem necessidade.
- Não aplicar refatorações amplas sem alinhamento.
- Não afirmar que algo foi testado se não foi.
- Não inventar arquivos, APIs, telas ou comportamentos.
- Não ocultar falhas, incertezas ou limitações.

## Preferências de execução

- Alterar somente o necessário.
- Ser objetivo.
- Otimizar uso de tokens.
- Priorizar soluções seguras e incrementais.
- Manter rastreabilidade das decisões.
- Sinalizar riscos antes de propor mudanças maiores.