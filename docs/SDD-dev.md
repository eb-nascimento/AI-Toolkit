# SDD Dev - Base de Registro por Implementacao

> Documento base para registro incremental durante o desenvolvimento.
> Este arquivo deve ser preenchido pela IA a cada implementacao, registrando apenas o escopo realmente tratado, decisoes tomadas, impactos e validacoes realizadas.
> Nao use este documento para antecipar requisitos ainda nao validados.

## 1. Identificacao

- Feature: Estruturacao do fluxo SDD, agentes e skills do repositorio
- Responsavel: IA
- Data: 2026-05-25
- Status: Implementado
- Agente/IA: Codex

## 2. Contexto

O repositorio e um estudo sobre SDD, skills e agentes. A estrutura inicial ja possuia modelos SDD, agentes de frontend/testes/revisao e skills de exemplo, mas faltava padronizar nomes, definir um agente SDD como regra de fluxo e criar uma skill para aprofundar requisitos antes da implementacao.

## 3. Objetivo

Organizar o repositorio para deixar explicito o fluxo SDD usado no desenvolvimento: `SDD-origin.md` como fonte de verdade e `SDD-dev.md` como registro da implementacao atual.

## 4. Escopo

### Dentro do escopo

- Padronizar a skill `frontend-accessibility`.
- Criar o agente `sdd-specialist`.
- Criar a skill `requirement-discovery`.
- Atualizar README, AGENTS, prompt SDD, Copilot instructions e agentes existentes para referenciar o fluxo SDD.
- Tornar o agente `code-reviewer` mais objetivo com prioridade de revisao.
- Tornar o agente `sdd-specialist` mais acionavel com criterios para parar e perguntar.
- Verificar referencias antigas e possiveis problemas de codificacao.

### Fora do escopo

- Criar exemplos preenchidos de SDD.
- Criar aplicacao executavel.
- Criar testes automatizados de codigo.
- Publicar novo commit ou PR.

## 5. Requisitos funcionais

### RF01 - Fluxo SDD obrigatorio para desenvolvimento

Toda tarefa de desenvolvimento deve considerar o agente `sdd-specialist` como referencia para delimitar requisito, escopo, criterios de aceite, validacoes e atualizacao dos documentos SDD.

#### Regras

- `docs/SDD-origin.md` deve ser tratado como fonte de verdade para requisitos e decisoes validadas.
- `docs/SDD-dev.md` deve registrar apenas o escopo realmente tratado na implementacao atual.
- Requisitos vagos devem usar a skill `requirement-discovery` antes da implementacao.
- Agentes executores devem preservar coerencia com o SDD.

#### Resultado esperado

- O repositorio deve orientar claramente quando usar `sdd-specialist`, `requirement-discovery` e as demais skills/agentes.

## 6. Requisitos nao funcionais

- Manter documentacao objetiva e rastreavel.
- Evitar dependencia externa.
- Preservar arquivos existentes e alterar apenas o necessario.
- Manter arquivos Markdown legiveis em UTF-8.

## 7. Criterios de aceite

- Dado um prompt de desenvolvimento, quando um agente consultar as instrucoes do repositorio, entao deve encontrar a regra de uso do `sdd-specialist`.
- Dado um requisito vago, quando a tarefa for analisada, entao deve existir uma skill dedicada para aprofundar requisito e testes esperados.
- Dado a skill de acessibilidade, quando o repositorio for navegado, entao o nome deve estar padronizado como `frontend-accessibility`.

## 8. Impactos

### Frontend

- Sem impacto em interface de aplicacao.

### Backend

- Sem impacto em backend.

### Dados

- Sem impacto em dados persistidos.

### Integracoes

- Impacto documental em GitHub Copilot instructions, agentes e prompts do repositorio.

## 9. Arquivos alterados

- `README.md`
- `AGENTS.md`
- `.github/copilot-instructions.md`
- `.github/prompts/atualizar-sdd.prompt.md`
- `.github/agents/code-reviewer.agent.md`
- `.github/agents/frontend-specialist.agent.md`
- `.github/agents/test-engineer.agent.md`
- `.github/agents/sdd-specialist.agent.md`
- `.github/skills/frontend-accessibility/SKILL.md`
- `.github/skills/requirement-discovery/SKILL.md`
- `docs/SDD-dev.md`

## 10. Decisoes tomadas

- Nao criar exemplos preenchidos de SDD porque o usuario informou que ja possui exemplo em outro repositorio.
- Padronizar o nome da pasta da skill para `frontend-accessibility`.
- Criar `sdd-specialist` como agente transversal para tarefas de desenvolvimento.
- Criar `requirement-discovery` como skill para aprofundar historias, requisitos incompletos e testes de aprovacao.
- Priorizar revisoes por divergencia de SDD, regra de negocio, seguranca, regressao, acessibilidade, arquitetura, testes e clareza.
- Definir pontos objetivos em que o `sdd-specialist` deve parar e pedir confirmacao.
- Nao regravar todos os arquivos para alterar encoding, pois a leitura com `-Encoding UTF8` confirmou que os acentos estao corretos.

## 11. Validacoes realizadas

- `rg --files --hidden -g !.git`
- Busca por nome antigo da skill e sequencias comuns de mojibake.
- `rg "[ \t]+$" --hidden -g !.git`
- `git diff --check`
- Leitura UTF-8 dos novos arquivos criados.

## 12. Riscos e premissas

### Riscos

- PowerShell sem `-Encoding UTF8` pode exibir mojibake mesmo quando os arquivos estao corretos em UTF-8.
- O repositorio ainda depende de convencao humana/agentes para aplicar o fluxo SDD, pois nao ha automacao que force o uso.

### Premissas

- O repositorio permanece como material de estudo e referencia, nao como aplicacao executavel.
- Exemplos preenchidos de SDD serao mantidos em outro repositorio compartilhado pelo usuario.

## 13. Pendencias

- Avaliar futuramente se vale criar automacao ou checklist para validar uso do fluxo SDD antes de merges.
