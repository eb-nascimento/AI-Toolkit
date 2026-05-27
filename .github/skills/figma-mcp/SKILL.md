---
name: figma-mcp
description: Use esta skill para auditar arquivos Figma e orientar agentes de IA/Codex/VS Code/Cursor na geração de código com MCP, priorizando fidelidade visual, reutilização de componentes, tokens, acessibilidade e atualização do SDD.
---

# Skill: Figma MCP Best Practices

## Objetivo

Ajudar o agente a usar o Figma MCP de forma controlada, verificável e aderente ao projeto, evitando geração de código baseada apenas em aparência visual e garantindo que o Figma seja tratado como fonte de contexto estruturado: componentes, variantes, tokens, auto layout, estilos, espaçamentos, assets e fluxos.

## Quando usar

Use esta skill quando a tarefa envolver:

- Implementar telas a partir de um link do Figma usando MCP.
- Auditar se um arquivo Figma está pronto para uso por agentes de IA.
- Converter layout Figma em código frontend.
- Comparar implementação existente com o design.
- Gerar ou atualizar componentes com base em design system.
- Avaliar consistência entre Figma, código e SDD.
- Criar prompts para Codex, Cursor, VS Code ou outro agente conectado ao Figma MCP.

## Pré-requisitos

Antes de implementar qualquer tela, confirme:

- O MCP do Figma está configurado no cliente/agente utilizado.
- O link informado aponta para um frame, seção ou componente específico, não apenas para o arquivo geral.
- O usuário tem permissão adequada no Figma.
- O projeto possui stack definida, por exemplo: React, Next.js, Flutter, Vue, HTML/CSS, Tailwind ou outra.
- O repositório possui padrões de componentes, rotas, estilos, tokens e estrutura de pastas.
- O SDD ou documentação técnica do projeto está disponível ou deve ser atualizado durante a tarefa.

## Checklist de qualidade do Figma para MCP

Avalie o arquivo Figma antes de gerar código.

### 1. Estrutura do arquivo

O arquivo deve ter páginas e frames nomeados de forma clara, como:

- `Cover`
- `Design System`
- `Components`
- `Flows`
- `Desktop`
- `Mobile`
- `Homologação`
- `Dev Ready`

Evite nomes genéricos como `Frame 123`, `Group 8`, `Copy 2` ou `Untitled`.

### 2. Seleção correta do escopo

Sempre trabalhe com o menor escopo possível:

- Para uma tela, usar o link do frame da tela.
- Para um componente, usar o link do componente ou component set.
- Para um fluxo, usar uma seção com frames relacionados.
- Para ajustes pontuais, usar o link da seleção específica.

Não peça ao agente para interpretar o arquivo inteiro sem necessidade.

### 3. Auto layout

Verifique se os principais blocos usam auto layout:

- Containers principais.
- Cards.
- Headers.
- Menus laterais.
- Botões.
- Inputs.
- Modais.
- Listas e tabelas.

Caso o design esteja baseado em grupos soltos e posições absolutas, sinalize risco de baixa responsividade e maior retrabalho na implementação.

### 4. Componentes e variantes

Confirme se elementos recorrentes estão componentizados:

- Botões.
- Campos de formulário.
- Cards.
- Badges/status.
- Menus.
- Abas.
- Modais.
- Tabelas.
- Componentes de feedback, como alertas, empty states e loading.

Verifique se há variantes para estados como:

- Default.
- Hover.
- Focus.
- Disabled.
- Loading.
- Error.
- Success.
- Selected.

### 5. Tokens, estilos e variáveis

Priorize designs que usam:

- Variáveis de cor.
- Estilos de texto.
- Tokens de espaçamento.
- Tokens de borda.
- Tokens de raio.
- Tokens de sombra.
- Temas, quando aplicável.

Evite copiar valores brutos sem verificar se há token correspondente no projeto.

### 6. Responsividade

Verifique se há orientação para:

- Desktop.
- Tablet, se aplicável.
- Mobile.
- Breakpoints.
- Comportamento de menus, tabelas e cards em telas menores.

Quando o projeto for visual-first ou pixel-preview, tamanhos fixos podem ser aceitos temporariamente para acelerar a estilização, mas devem ser sinalizados como etapa intermediária, não como solução final responsiva.

### 7. Acessibilidade

Antes de implementar, validar:

- Hierarquia de títulos.
- Contraste de cores.
- Estados de foco.
- Labels de campos.
- Áreas clicáveis adequadas.
- Navegação por teclado.
- Textos alternativos para imagens relevantes.
- Feedbacks de erro compreensíveis.

### 8. Assets e ícones

Verifique se:

- Ícones fazem parte de uma biblioteca consistente.
- Imagens têm nome claro.
- Logos e imagens institucionais têm versão correta.
- Assets exportáveis estão marcados corretamente.
- SVGs não foram convertidos desnecessariamente em imagens rasterizadas.

### 9. Dev Mode e handoff

Procure evidências de preparo para desenvolvimento:

- Frames finais marcados como prontos para desenvolvimento.
- Comentários resolvidos ou tratados.
- Regras de comportamento documentadas.
- Estados de tela disponíveis.
- Fluxos de navegação claros.
- Textos reais ou exemplos próximos do conteúdo final.

### 10. Code Connect e design system

Quando houver design system e repositório com componentes reais:

- Priorize reutilizar componentes existentes.
- Mapear componentes Figma para componentes do código.
- Evitar recriar componentes que já existem.
- Usar Code Connect quando disponível.
- Registrar divergências entre design e implementação.

## Fluxo recomendado de trabalho com MCP

### Etapa 1 — Entendimento

Antes de codificar, o agente deve:

1. Ler o link do frame/seleção via MCP.
2. Identificar layout, componentes, tokens, textos, estados e assets.
3. Verificar se existe componente equivalente no repositório.
4. Identificar dependências técnicas e padrões existentes.
5. Confirmar se a tela está pronta para implementação ou se há lacunas.

### Etapa 2 — Auditoria rápida do Figma

Classifique o design como:

- **Pronto para MCP**: componentes, auto layout, tokens, nomes claros e estados definidos.
- **Parcialmente pronto**: estrutura visual clara, mas com lacunas em responsividade, tokens ou estados.
- **Risco alto**: grupos soltos, nomes genéricos, sem componentes, sem estados e sem regras de comportamento.

Quando houver risco, informe antes de implementar.

### Etapa 3 — Planejamento da implementação

Antes de alterar código:

- Identifique arquivos afetados.
- Defina componentes a reutilizar.
- Defina novos componentes necessários.
- Defina estilos/tokens a aplicar.
- Defina rotas, props, estados e integrações.
- Atualize o SDD com decisões relevantes.

### Etapa 4 — Implementação

Regras obrigatórias:

- Não editar linha por linha; aplicar alterações em bloco único/consolidado.
- Manter o SDD atualizado com alterações, adições e ajustes realizados.
- Usar componentes existentes antes de criar novos.
- Evitar hardcode quando houver tokens ou constantes do projeto.
- Separar layout, comportamento e dados quando a arquitetura do projeto permitir.
- Não implementar regras de negócio inexistentes no Figma sem sinalizar suposição.
- Não alterar padrões globais sem justificar impacto.

### Etapa 5 — Validação

Após implementar:

- Comparar a tela com o frame Figma.
- Validar espaçamentos, tipografia, cores, estados e responsividade.
- Verificar console, lint, build e testes disponíveis.
- Registrar divergências conhecidas.
- Atualizar SDD, README ou documentação aplicável.

## Prompts recomendados

### Auditar Figma antes de implementar

```text
Use o Figma MCP para analisar este frame: <URL_DO_FRAME>.
Avalie se ele está pronto para implementação com IA, considerando: nomes de camadas, auto layout, componentes, variantes, tokens, responsividade, acessibilidade, assets e clareza do fluxo.
Retorne uma classificação: Pronto para MCP, Parcialmente pronto ou Risco alto.
Liste apenas os pontos que impactam diretamente a implementação.
Não altere código ainda.