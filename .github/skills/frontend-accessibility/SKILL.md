---
name: frontend-accessibility
description: Use esta skill ao criar, revisar, refatorar ou validar interfaces frontend com foco em acessibilidade, semântica HTML, navegação por teclado, foco, formulários, contraste, ARIA, tabelas, modais, mensagens de erro, imagens, SVGs e responsividade.
---

# Frontend Accessibility

Use esta skill para orientar revisões e melhorias de acessibilidade em interfaces frontend.

## Objetivo

Garantir que componentes, páginas e fluxos frontend sejam mais acessíveis, navegáveis e compreensíveis para diferentes perfis de usuários, incluindo pessoas que utilizam teclado, leitores de tela, zoom, alto contraste ou tecnologias assistivas.

## Regras principais

- Priorizar HTML semântico antes de usar ARIA.
- Usar ARIA apenas quando o HTML nativo não resolver.
- Não remover funcionalidades existentes.
- Não alterar regras de negócio.
- Não reescrever a interface inteira sem necessidade.
- Não adicionar dependências externas sem solicitação.
- Não mascarar problemas de acessibilidade apenas com atributos ARIA.
- Preservar padrões do projeto, componentes existentes e estrutura de estilos.
- Propor ajustes mínimos, seguros e sem regressão visual ou funcional.
- Não afirmar conformidade total sem validação completa.

## Checklist de análise

### Estrutura semântica

Verificar se a interface usa elementos adequados:

- `button` para ações.
- `a` para navegação.
- `form`, `label`, `input`, `select` e `textarea` para formulários.
- `table`, `thead`, `tbody`, `tr`, `th` e `td` para tabelas reais.
- `header`, `main`, `nav`, `section`, `article`, `aside` e `footer` quando fizer sentido.

Evitar excesso de `div` e `span` em elementos interativos.

### Navegação por teclado

Validar se:

- Todos os elementos interativos podem ser acessados por teclado.
- A ordem de tabulação segue a ordem visual e lógica da tela.
- Não há armadilhas de foco.
- Elementos clicáveis não dependem apenas de `onClick` em `div` ou `span`.
- Ações importantes funcionam com `Enter` e/ou `Space`.

### Foco visível

Validar se:

- O foco é visível em botões, links, campos e controles.
- Não há remoção de `outline` sem substituição acessível.
- Estados `focus`, `hover`, `active` e `disabled` estão coerentes.

### Formulários

Verificar se:

- Todo campo possui `label` associado corretamente.
- Placeholder não é usado como único rótulo.
- Campos obrigatórios são identificados.
- Mensagens de erro são claras.
- Erros são associados aos campos quando possível.
- Inputs usam tipos adequados, como `email`, `tel`, `number`, `date`, entre outros.
- Campos possuem `autocomplete` quando aplicável.

### Botões e links

Validar se:

- Botões possuem texto acessível.
- Ícones clicáveis possuem `aria-label` quando não há texto visível.
- Links descrevem o destino ou ação.
- Não há links genéricos como “clique aqui” sem contexto.

### Imagens, ícones e SVGs

Verificar se:

- Imagens informativas possuem `alt` descritivo.
- Imagens decorativas usam `alt=""`.
- SVGs decorativos usam `aria-hidden="true"`.
- SVGs funcionais possuem rótulo acessível.

### Cores e contraste

Validar se:

- Texto e fundo possuem contraste adequado.
- Informação não depende apenas de cor.
- Estados de erro, sucesso ou alerta possuem texto, ícone ou reforço além da cor.

### Tabelas

Verificar se:

- Tabelas reais usam estrutura de tabela, não apenas layout visual.
- Cabeçalhos usam `th`.
- Cabeçalhos possuem `scope` quando aplicável.
- A leitura por tecnologia assistiva mantém sentido.

### Modais, menus e overlays

Quando houver modais, menus ou overlays:

- Controlar foco ao abrir e fechar.
- Permitir fechar com `Esc`, quando aplicável.
- Usar rótulo acessível.
- Evitar que o foco vá para conteúdo atrás do modal.
- Retornar foco ao elemento que abriu o modal.

### Movimento e animação

Verificar se:

- Animações não prejudicam leitura ou navegação.
- Transições intensas respeitam `prefers-reduced-motion`.
- Não há autoplay intrusivo sem controle.

### Responsividade e zoom

Validar se:

- A interface continua utilizável com zoom.
- Conteúdo não fica cortado sem alternativa.
- Campos e botões continuam acessíveis em telas menores.
- Textos não dependem de tamanho fixo quando isso prejudicar leitura.

## Processo recomendado

Ao revisar uma interface:

1. Identificar os elementos interativos.
2. Verificar semântica HTML.
3. Validar navegação por teclado e foco.
4. Revisar formulários e mensagens de erro.
5. Revisar tabelas, modais, menus e componentes especiais.
6. Verificar contraste, texto alternativo e uso de ARIA.
7. Propor ajustes mínimos e seguros.
8. Informar riscos restantes, se houver.

## Formato de resposta esperado

Resumo:

- O que foi analisado.

Problemas encontrados:

- Lista objetiva dos pontos de acessibilidade.

Correções sugeridas/aplicadas:

- Ajustes realizados ou recomendados.

Riscos restantes:

- Pontos que ainda precisam de validação manual.
