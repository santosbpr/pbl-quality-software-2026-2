# Atividade 2: Organização da Qualidade no LocalEats

### Tarefa 1: Diagnóstico da situação

| Problema identificado | Possível consequência para o produto ou para a equipe |
| :--- | :--- |
| Funcionalidades chegam com defeitos aos usuários e ausência de critérios claros de aceitação ("Definition of Done"). | Aumento do retrabalho, entregas inconsistentes e frustração dos clientes que utilizam o LocalEats. |
| Defeitos identificados não são registrados ou acompanhados adequadamente. | Reincidência de bugs conhecidos, perda de histórico e acúmulo de débito técnico sem priorização de correção. |
| Indefinição sobre a responsabilidade de aprovação de versões e sobreposição/ausência de responsáveis por tarefas. | Conflito na tomada de decisão, gargalos na liberação de versões para produção e risco de deploys inseguros. |

**Pergunta reflexiva:**
Não. A qualidade deve ser uma responsabilidade compartilhada por toda a equipe ("Quality is built in"). Os desenvolvedores constroem a qualidade escrevendo código limpo e testes unitários; o Responsável pelo Produto garante critérios de aceitação claros; e o QA atua como um facilitador de boas práticas, automação e estratégia de testes. Concentrar a qualidade apenas no QA cria um gargalo no processo e aumenta os riscos de falhas no produto final.

---
### Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
| :--- | :--- | :--- | :--- | :--- |
| Breno Prado dos Santos | Responsável pelo Produto (PO) | Definir critérios de aceitação claros nas histórias de usuário, revisar requisitos e priorizar a correção de defeitos no backlog conforme o impacto no negócio. | Gestão de backlog, escrita de critérios de aceite (BDD), visão de produto e domínio de metodologias ágeis. | Comunicação clara, negociação, visão crítica de negócio e capacidade de decisão. |
| Breno Prado dos Santos | Desenvolvedor | Escrever código limpo e sustentável, criar e manter testes unitários, realizar revisão de código (*code review*) e implementar as funcionalidades com foco na prevenção de bugs. | Engenharia de software, boas práticas (Clean Code, SOLID), ferramentas de testes unitários e integração contínua (CI). | Colaboração, atenção aos detalhes, orientação à resolução de problemas e responsabilidade com a entrega. |
| Breno Prado dos Santos | Analista de Qualidade (QA) | Planejar e executar a estratégia de testes do sistema, registrar e acompanhar defeitos, apoiar o time na definição de cenários e promover a automação de testes. | Metodologias e técnicas de teste, automação de testes (API/E2E), análise de causas raízes de falhas e métricas de qualidade. | Pensamento crítico, empatia com o usuário final, excelente comunicação interpessoal e mentalidade investigativa. |

---
### Tarefa 3: Matriz de responsabilidades (RACI)

1. **R (Responsável):** Quem executa a atividade (pode ter mais de um por linha).
2. **A (Aprovador):** Quem responde pelo resultado final e toma a decisão (**deve ser ÚNICO por linha**).
3. **C (Consultado):** Quem contribui com informações antes da decisão/execução.
4. **I (Informado):** Quem é avisado sobre o resultado.
---
| Atividade de qualidade | Responsável pelo Produto (PO) | Desenvolvedor | Analista de Qualidade (QA) |
| :--- | :---: | :---: | :---: |
| **Definir critérios de aceitação** | R, A | C | C |
| **Revisar requisitos** | A | R | R |
| **Implementar a funcionalidade** | I | R, A | I |
| **Revisar o código (Code Review)** | I | R, A | I |
| **Criar testes unitários** | I | R, A | C |
| **Planejar e executar testes do sistema** | I | C | R, A |
| **Registrar e acompanhar defeitos** | I | R | R, A |
| **Priorizar a correção dos defeitos** | R, A | C | C |
| **Aprovar a disponibilização da versão** | R, A | I | C |

---

### Lacuna ou conflito encontrado

&gt; **Conflito de Responsabilidade no Release e Ausência de Critérios Prontos:**
&gt; Antes da organização, a aprovação de versões para produção ficava informal ou concentrada exclusivamente no QA, gerando gargalos e indefinição sobre o aceite final de negócio. A matriz RACI resolveu o conflito ao estabelecer o **PO como único Aprovador (A)** da disponibilização da versão, fundamentado no parecer técnico e relatório de testes emitido pelo QA (Consultado - C).

---

### Práticas recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
| :--- | :--- | :--- |
| **Reunião de "Three Amigos" (Refinamento BDD)** | Requisitos vagos e critérios de aceitação ausentes/incompletos no início da sprint. | PO, Desenvolvedor e QA. |
| **Adoção de Definition of Done (DoD) e Definition of Ready (DoR)** | Funcionalidades chegando com defeitos em produção e falta de clareza sobre quando a tarefa está pronta. | PO, Desenvolvedor e QA. |

---
## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini Notebook.

**Como foi utilizada:**
Auxílio na estruturação das tabelas em Markdown, diagnóstico dos problemas organizacionais do LocalEats e apoio na consolidação da matriz RACI com papéis e práticas recomendadas de QA.

**Como as respostas foram verificadas:**
O conteúdo gerado foi revisado e validado quanto à coerência técnica, garantindo o cumprimento estrito das regras do RACI (como a existência de um único Aprovador por atividade) e alinhamento com as orientações da disciplina.


```