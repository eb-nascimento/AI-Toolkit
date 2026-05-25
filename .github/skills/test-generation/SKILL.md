---
name: test-generation
description: Use esta skill ao criar, revisar, refatorar ou ampliar testes automatizados, incluindo testes unitários, integração, componentes, APIs, fluxos críticos, mocks, casos de borda e prevenção de regressões.
---

# Test Generation

Use esta skill para orientar a criação e revisão de testes automatizados em projetos de software.

## Objetivo

Garantir que novas funcionalidades, correções e refatorações sejam acompanhadas por testes claros, úteis e sustentáveis, reduzindo regressões e aumentando a confiança nas alterações.

## Regras principais

- Priorizar testes que validem comportamento, não detalhes internos de implementação.
- Não criar testes frágeis dependentes de estrutura interna desnecessária.
- Não alterar regra de negócio apenas para facilitar teste.
- Não remover testes existentes sem justificativa.
- Não ignorar cenários de erro, borda ou permissão.
- Não adicionar dependências externas sem solicitação.
- Manter o padrão de testes já utilizado no projeto.
- Criar testes pequenos, legíveis e objetivos.
- Usar nomes descritivos para os cenários testados.
- Quando não for possível testar algo, explicar a limitação.

## Checklist de análise

### Entendimento do escopo

Antes de criar testes, identificar:

- Qual comportamento precisa ser validado.
- Qual alteração foi feita no código.
- Quais fluxos podem quebrar.
- Quais entradas e saídas são esperadas.
- Quais regras de negócio estão envolvidas.
- Quais dependências externas precisam ser simuladas.

### Tipos de teste

Avaliar qual tipo de teste faz mais sentido:

- Teste unitário para funções, métodos e regras isoladas.
- Teste de componente para interface e comportamento visual/interativo.
- Teste de integração para comunicação entre módulos.
- Teste de API para contratos, status codes e payloads.
- Teste end-to-end para fluxos críticos do usuário.
- Teste de regressão para bugs corrigidos.
- Teste de acessibilidade quando houver impacto em interface.

### Casos positivos

Verificar se os testes cobrem:

- Fluxo principal esperado.
- Entrada válida.
- Resposta ou renderização correta.
- Estado final esperado.
- Chamadas corretas a funções, serviços ou APIs quando aplicável.

### Casos negativos

Verificar se os testes cobrem:

- Entrada inválida.
- Dados ausentes.
- Erros de validação.
- Falha de API ou serviço externo.
- Permissão insuficiente.
- Usuário não autenticado.
- Estado vazio.
- Timeout ou indisponibilidade quando aplicável.

### Casos de borda

Considerar:

- Valores nulos ou indefinidos.
- Lista vazia.
- Lista com um item.
- Lista com muitos itens.
- Datas no limite.
- Valores mínimos e máximos.
- Strings vazias ou muito longas.
- Caracteres especiais.
- Diferenças de timezone quando houver datas.
- Duplicidade de dados.
- Estados concorrentes ou repetidos.

### Mocks e dependências

Ao usar mocks:

- Simular apenas o necessário.
- Evitar mocks excessivamente complexos.
- Manter dados de teste claros e realistas.
- Isolar chamadas externas, como APIs, banco, autenticação, storage ou serviços de terceiros.
- Garantir que mocks não escondam problemas reais de contrato.

### Testes de frontend

Em interfaces, validar:

- Renderização dos elementos principais.
- Estados de loading, erro, vazio e sucesso.
- Interações do usuário.
- Campos obrigatórios.
- Mensagens de erro.
- Navegação esperada.
- Acessibilidade básica, como labels, roles e foco, quando aplicável.
- Não depender de textos instáveis quando houver seletores mais adequados.

### Testes de backend

Em backend, validar:

- Entrada da função ou endpoint.
- Status code esperado.
- Payload de resposta.
- Tratamento de erro.
- Validações obrigatórias.
- Persistência ou atualização de dados.
- Regras de autorização.
- Efeitos colaterais esperados, como filas, eventos, logs ou chamadas externas.

### Testes de regressão

Para bugs corrigidos:

- Criar pelo menos um teste que falharia antes da correção.
- Nomear o cenário de forma clara.
- Validar o comportamento corrigido.
- Evitar testar apenas a implementação da correção.

## Processo recomendado

Ao gerar testes:

1. Ler o código alterado e entender o comportamento esperado.
2. Identificar riscos de regressão.
3. Verificar padrões de teste existentes no projeto.
4. Criar casos positivos, negativos e de borda.
5. Usar mocks apenas quando necessário.
6. Rodar ou orientar a execução dos testes.
7. Ajustar testes frágeis ou redundantes.
8. Informar lacunas que ainda exigem validação manual.

## Formato de resposta esperado

Resumo:

- O que foi testado.

Testes criados/sugeridos:

- Lista objetiva dos cenários cobertos.

Casos considerados:

- Positivos, negativos e borda.

Como executar:

- Comando ou orientação para rodar os testes.

Riscos restantes:

- Pontos que ainda precisam de validação manual ou integração.
