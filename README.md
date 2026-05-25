# AI Toolkit

Repositório-base para iniciar novos projetos com uso organizado de IA no desenvolvimento de software.

O foco é fornecer uma estrutura reutilizável para:

- SDD (Spec Driven Development);
- agentes de IA;
- prompts reutilizáveis;
- skills;
- GitHub Copilot / Codex / VS Code Agents;
- MCP e fluxos assistidos por IA;
- revisão, testes e acessibilidade.

---

## Objetivo

Servir como ponto de partida para novos projetos, mantendo instruções, agentes, prompts, skills e os dois arquivos SDD que serão preenchidos durante a implementação real.

Este repositório não é uma aplicação executável. Ele é uma base de trabalho para copiar, adaptar ou usar como referência em projetos futuros.

---

## Estrutura

```text
.github/
  copilot-instructions.md
  prompts/
    atualizar-sdd.prompt.md
    revisar-repositorio-sdd.prompt.md
  agents/
    sdd-specialist.agent.md
    frontend-specialist.agent.md
    test-engineer.agent.md
    code-reviewer.agent.md
  skills/
    frontend-accessibility/
      SKILL.md
    test-generation/
      SKILL.md
    requirement-discovery/
      SKILL.md

docs/
  SDD-origin.md
  SDD-dev.md

AGENTS.md
README.md
.editorconfig
.gitattributes
```

---

## Fluxo SDD

Este repositório mantém somente dois arquivos SDD:

- `docs/SDD-origin.md`: fonte de verdade do projeto real, preenchida com requisitos, regras, fluxos e decisões validadas.
- `docs/SDD-dev.md`: registro da implementação atual, preenchido a cada tarefa com escopo tratado, decisões, arquivos alterados, validações e pendências.

Não crie arquivos `SDD-*.template.md` separados. Os dois arquivos acima já são os modelos canônicos que devem ser preenchidos no projeto que usar esta base.

Toda tarefa de desenvolvimento deve passar por:

1. entendimento do requisito;
2. delimitação de escopo;
3. critérios de aceite;
4. implementação ou orientação técnica;
5. validações;
6. atualização do SDD quando necessário.

---

## Uso em Novo Projeto

1. Copie esta estrutura para o novo repositório.
2. Preencha `docs/SDD-origin.md` com o contexto e os requisitos validados do projeto.
3. Use `docs/SDD-dev.md` para registrar cada implementação.
4. Ajuste agentes, prompts e skills apenas quando o projeto tiver regras específicas.
5. Mantenha `SDD-origin.md` como fonte de verdade e `SDD-dev.md` como registro da tarefa atual.

---

## Agentes

- `sdd-specialist`: guardião de requisitos, escopo, critérios de aceite e SDD.
- `frontend-specialist`: especialista em interface, componentização, responsividade e acessibilidade.
- `test-engineer`: especialista em testes, validação e prevenção de regressão.
- `code-reviewer`: revisor técnico com foco em arquitetura, segurança, qualidade e aprendizado.

---

## Skills

- `frontend-accessibility`: revisão e melhoria de acessibilidade frontend.
- `test-generation`: criação e revisão de testes automatizados.
- `requirement-discovery`: descoberta e refinamento de requisitos antes da implementação.

---

## Prompts Reutilizáveis

- `atualizar-sdd.prompt.md`: usado para manter documentação SDD atualizada.
- `revisar-repositorio-sdd.prompt.md`: usado para revisar consistência entre SDD, agentes, prompts e skills.

---

## Boas Práticas

- Não inventar requisitos.
- Não alterar regra de negócio sem confirmação.
- Não remover histórico funcional.
- Não registrar no SDD comportamento não implementado.
- Não editar linha por linha; aplicar alterações em bloco único/consolidado.
- Priorizar soluções simples, seguras, testáveis e rastreáveis.
- Informar limitações e validações pendentes.
