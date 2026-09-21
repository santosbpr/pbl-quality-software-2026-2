# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## Tarefa 1: Planejamento dos testes

### 1.1 Objetivo dos testes
Verificar se a funcionalidade de pesquisa e filtragem de restaurantes por especialidade e localização exibe corretamente apenas os estabelecimentos correspondentes à busca e apresenta feedback visual claro em cenários de busca sem resultados ou com termos inválidos.

### 1.2 Escopo

| **Integrante** | **Funcionalidade incluída** | **O que será verificado** |
| :--- | :--- | :--- |
| Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | Seleção de especialidade cadastrada, busca textual de restaurante/categoria e comportamento do sistema em buscas sem correspondência. |

| **Funcionalidade não incluída** | **Justificativa** |
| :--- | :--- |
| Fazer pedido | Não faz parte do escopo de catalogação e navegação de restaurantes delimitado para este plano individual. |

### 1.3 Abordagem

| **Item** | **Decisão da equipe** | **Justificativa** |
| :--- | :--- | :--- |
| **Níveis de teste** | Sistema | O fluxo de pesquisa e filtragem será avaliado do início ao fim diretamente na interface gráfica. |
| **Tipos de teste** | Funcional | O objetivo é verificar a aplicação das regras de exibição e filtragem de restaurantes. |
| **Perspectiva** | Caixa-preta | Serão analisados os dados de entrada fornecidos pelo usuário e as respostas observáveis na tela, sem acesso ao código-fonte. |
| **Técnicas de teste** | Particionamento de equivalência | A funcionalidade aceita diferentes classes de dados de entrada (válidos e inválidos), sendo ideal para o agrupamento em classes representativas. |

### 1.4 Ambiente e responsabilidades

| **Item** | **Definição** |
| :--- | :--- |
| **Ambiente necessário** | Navegador (Google Chrome / Mozilla Firefox), conexão com a internet, dispositivo desktop ou mobile e acesso à aplicação em `https://local-eats-unisenac.vercel.app/`. |
| **Responsáveis pelo planejamento** | Breno Prado dos Santos |
| **Responsáveis pela especificação dos casos** | Breno Prado dos Santos |
| **Responsáveis pela futura execução** | Breno Prado dos Santos |

### 1.5 Critérios

| **Critério** | **Definição** |
| :--- | :--- |
| **Entrada** | Aplicação LocalEats acessível no ambiente Vercel, lista de restaurantes cadastrada e campo de pesquisa/filtro ativo. |
| **Saída** | Todos os 3 casos de teste (CT01 a CT03) especificados, revisados e com a matriz de rastreabilidade concluída. |
| **Suspensão** | Indisponibilidade do ambiente Vercel ou falha crítica que impeça o carregamento da tela principal do LocalEats. |

---

## Tarefa 2: Riscos e técnicas de teste

### 2.1 Análise dos riscos

| **ID** | **Integrante** | **Funcionalidade** | **Risco** | **Consequência** | **Probabilidade** | **Impacto** | **Prioridade** | **Justificativa** |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R01** | Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | Exibição de restaurantes incorretos ou não pertencentes à especialidade/localização pesquisada. | O cliente escolhe um restaurante errado, gerando insatisfação com a plataforma e perda de confiabilidade. | Média | Alto | **Alta** | Afeta diretamente o propósito do sistema de conectar usuários aos restaurantes corretos. |
| **R02** | Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | Ausência de feedback visual quando a pesquisa não retornar resultados (tela travada, em branco ou sem aviso). | O usuário assume que o aplicativo quebrou e abandona o sistema por falta de orientação. | Média | Alto | **Alta** | Compromete a usabilidade e a experiência de navegação do usuário. |

### 2.2 Aplicação da técnica

**Integrante responsável:** Breno Prado dos Santos  
**Funcionalidade:** Pesquisar/Filtrar restaurantes por especialidade ou localização  
**Risco relacionado:** R01 e R02  
**Técnica escolhida:** Particionamento de Equivalência  

**Por que a técnica foi escolhida?**  
A busca aceita variados tipos de entrada (categorias com estabelecimentos ativos, categorias sem restaurantes no momento e caracteres ou termos inexistentes). O Particionamento de Equivalência permite dividir esses dados em classes equivalentes, garantindo alta cobertura de testes com um número reduzido e representativo de cenários.

**Aplicação da técnica (Classes de Equivalência):**

| **Classe** | **Situação / Regra** | **Valor representativo** | **Resultado Esperado** |
| :--- | :--- | :--- | :--- |
| **C1 (Válida)** | Especialidade cadastrada que possui restaurantes ativos. | "Japonesa" | Exibir apenas restaurantes da categoria "Japonesa". |
| **C2 (Válida)** | Especialidade/termo válido, porém sem restaurantes disponíveis. | "Vegana" | Exibir a mensagem: "Nenhum restaurante encontrado." |
| **C3 (Inválida)** | Inserção de caracteres especiais ou termos inexistentes. | `@#$%!` | Sanitizar busca e exibir a mensagem de aviso na tela sem disparar erros. |

**Casos derivados:**
* **CT01**: Filtrar restaurantes por especialidade válida com resultados (derivado da Classe C1).
* **CT02**: Buscar por termo/especialidade sem estabelecimentos associados (derivado da Classe C2 e Risco R02).
* **CT03**: Buscar inserindo caracteres especiais ou entradas inválidas (derivado da Classe C3 e Risco R02).

---

## Tarefa 3: Casos de teste e rastreabilidade

### 3.1 Especificação dos casos de teste

**CT01: Filtrar restaurantes por especialidade válida com resultados**  

**Integrante responsável:** Breno Prado dos Santos  
**Funcionalidade:** Pesquisar/Filtrar restaurantes por especialidade ou localização  
**Risco ou requisito relacionado:** R01 (Exibição de restaurantes incorretos)  
**Técnica utilizada:** Particionamento de Equivalência (Classe C1)  
**Pré-condição:**  
O usuário está na página inicial do LocalEats e a lista de restaurantes está carregada.  
**Dados de entrada:**  
Filtro selecionado: "Japonesa".  
**Passos:**  
1. Acessar a página inicial do LocalEats.  
2. Localizar os botões de filtro por categoria.  
3. Clicar na categoria "Japonesa".  
**Resultado esperado:**  
A lista de restaurantes é filtrada e exibe exclusivamente os estabelecimentos cadastrados na especialidade "Japonesa".  

---

**CT02: Buscar por termo/especialidade sem estabelecimentos associados**  

**Integrante responsável:** Breno Prado dos Santos  
**Funcionalidade:** Pesquisar/Filtrar restaurantes por especialidade ou localização  
**Risco ou requisito relacionado:** R02 (Ausência de feedback em busca nula)  
**Técnica utilizada:** Particionamento de Equivalência (Classe C2)  
**Pré-condição:**  
O usuário está na página inicial com o campo de busca ativado.  
**Dados de entrada:**  
Texto digitado no campo de busca: "Vegana".  
**Passos:**  
1. Acessar a tela inicial da aplicação.  
2. Digitar o termo "Vegana" no campo de busca.  
3. Clicar no botão "Buscar".  
**Resultado esperado:**  
O sistema atualiza a tela e exibe claramente a mensagem orientativa: "Nenhum restaurante encontrado.", sem travar ou deixar a tela em branco.  

---

**CT03: Buscar inserindo caracteres especiais ou entradas inválidas**  

**Integrante responsável:** Breno Prado dos Santos  
**Funcionalidade:** Pesquisar/Filtrar restaurantes por especialidade ou localização  
**Risco ou requisito relacionado:** R02 (Ausência de feedback e proteção contra erros)  
**Técnica utilizada:** Particionamento de Equivalência (Classe C3)  
**Pré-condição:**  
O usuário está na página inicial do LocalEats.  
**Dados de entrada:**  
Texto digitado no campo de busca: `@#$%!`.  
**Passos:**  
1. Digitar a sequência de caracteres `@#$%!` no campo de busca.  
2. Clicar no botão "Buscar".  
**Resultado esperado:**  
O sistema trata a entrada de forma segura, não apresenta erros técnicos e exibe a mensagem de aviso: "Nenhum restaurante encontrado.".  

---

### 3.2 Matriz de rastreabilidade

| **Integrante** | **Funcionalidade** | **Risco ou requisito** | **Técnica utilizada** | **Casos de teste** |
| :--- | :--- | :--- | :--- | :--- |
| Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | R01: Exibição de restaurantes incorretos | Particionamento de Equivalência (Classe C1) | CT01 |
| Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | R02: Ausência de feedback em busca nula | Particionamento de Equivalência (Classe C2) | CT02 |
| Breno Prado dos Santos | Pesquisar/Filtrar restaurantes por especialidade ou localização | R02: Entrada de caracteres inválidos | Particionamento de Equivalência (Classe C3) | CT03 |

---

## Uso de inteligência artificial

**Ferramenta utilizada:**  
Gemini Notebook.  

**Como foi utilizada:**  
Apoio no planejamento simplificado de testes, identificação dos riscos da funcionalidade de busca e aplicação do Particionamento de Equivalência com derivação dos casos de teste (CT01, CT02, CT03) rastreáveis.  

**Uma sugestão que precisou ser alterada ou rejeitada:**  
A sugestão inicial da IA de utilizar a funcionalidade de checkout ("Fazer pedido") com a técnica de *Tabela de Decisão* foi alterada para *Particionamento de Equivalência* na funcionalidade de filtragem, mantendo a coerência com a funcionalidade explorada nas atividades anteriores.  

**Como as respostas foram verificadas:**  
A matriz de rastreabilidade, as classes de equivalência e a redação dos passos foram revisadas manualmente para confirmar total alinhamento com as regras e diretrizes do guia do PBL.
