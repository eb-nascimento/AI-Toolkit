# AI Toolkit

[Português](#português) · [English](#english)

## Português

Base reutilizável de agentes, prompts, skills e documentação para organizar o desenvolvimento de software assistido por IA.

Criado como estudo de fluxos com IA, MCP e **SDD (Spec Driven Development)**, o toolkit reúne orientações que considero úteis para transformar requisitos em implementações com escopo, contexto e validações explícitos. Entre os interesses que motivaram o estudo está o desenvolvimento frontend a partir de designs do Figma.

### O que você encontra aqui

- Agentes especializados em requisitos e SDD, frontend, testes e revisão de código.
- Skills para descoberta de requisitos, acessibilidade frontend e geração de testes.
- Prompts reutilizáveis para atualizar documentação e revisar sua consistência.
- Instruções para agentes e GitHub Copilot.
- Documentos-base para registrar requisitos e implementação.

### Organização

```text
.github/
  agents/
  prompts/
  skills/
  copilot-instructions.md
docs/
  SDD-origin.md
  SDD-dev.md
AGENTS.md
```

### Como utilizar

1. Copie a estrutura relevante para o seu projeto.
2. Preencha `docs/SDD-origin.md` com contexto, requisitos, regras e critérios de aceite validados.
3. Use `docs/SDD-dev.md` para registrar a implementação atual, decisões, validações e pendências.
4. Adapte os agentes, prompts e skills ao domínio e à ferramenta utilizada.
5. Trabalhe com tarefas delimitadas e confira o resultado antes de atualizar a documentação.

Os dois documentos SDD são os modelos canônicos da estrutura; não é necessário criar cópias `SDD-*.template.md`.

### Princípios

- Esclarecer requisitos antes de implementar.
- Manter o escopo e os critérios de aceite visíveis.
- Priorizar simplicidade, acessibilidade e validações relevantes.
- Documentar o que foi implementado e explicitar o que continua pendente.
- Revisar as sugestões da IA com contexto e julgamento técnico.

### Estágio e limites

Este é um estudo e uma base de trabalho adaptável, não uma aplicação executável. A forma de carregar agentes, prompts e skills depende da ferramenta utilizada, como Codex ou GitHub Copilot no VS Code. Configurações de MCP e permissões devem ser ajustadas ao ambiente de cada projeto.

---

## English

A reusable collection of agents, prompts, skills, and documentation for organizing AI-assisted software development.

Created as a study of AI workflows, MCP, and **Spec Driven Development (SDD)**, this toolkit brings together guidance I find useful for turning requirements into implementations with explicit scope, context, and validation. One motivation behind the study is frontend development based on Figma designs.

### Contents

- Specialized agents for requirements and SDD, frontend, testing, and code review.
- Skills for requirement discovery, frontend accessibility, and test generation.
- Reusable prompts for updating documentation and reviewing its consistency.
- Instructions for agents and GitHub Copilot.
- Base documents for recording requirements and implementation.

### Structure

```text
.github/
  agents/
  prompts/
  skills/
  copilot-instructions.md
docs/
  SDD-origin.md
  SDD-dev.md
AGENTS.md
```

### Usage

1. Copy the relevant structure into your project.
2. Fill in `docs/SDD-origin.md` with validated context, requirements, rules, and acceptance criteria.
3. Use `docs/SDD-dev.md` to record the current implementation, decisions, validation, and remaining work.
4. Adapt agents, prompts, and skills to your domain and tool.
5. Work on clearly scoped tasks and check the results before updating the documentation.

The two SDD documents are the canonical starting documents; separate `SDD-*.template.md` copies are unnecessary.

### Principles

- Clarify requirements before implementation.
- Keep scope and acceptance criteria visible.
- Favor simplicity, accessibility, and relevant validation.
- Document implemented behavior and make remaining work explicit.
- Review AI suggestions using project context and technical judgment.

### Status and limitations

This is a study and an adaptable workflow foundation, not an executable application. Loading agents, prompts, and skills depends on the chosen tool, such as Codex or GitHub Copilot in VS Code. MCP settings and permissions must be adapted to each project's environment.
