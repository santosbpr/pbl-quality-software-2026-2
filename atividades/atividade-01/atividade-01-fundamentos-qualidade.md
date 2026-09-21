### Tarefa 1: Fundamentos da qualidade

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
| :--- | :--- | :--- | :--- |
| Explícita | Permitir a pesquisa e filtragem de restaurantes por especialidade e localização. | Cliente / Usuário final | O cliente não encontra o restaurante desejado, gerando frustração e abandono do aplicativo. |
| Explícita | Exibir o histórico e o status atualizado dos pedidos. | Cliente e Restaurante | Falta de visibilidade sobre a entrega, gerando ansiedade no cliente e aumento de chamados de suporte. |
| Implícita | Garantir tempo de resposta ágil ao carregar cardápios e efetuar buscas. | Cliente e Negócio | O usuário percebe o sistema como lento ou ineficiente e migra para plataformas concorrentes. |
| Implícita | Apresentar mensagens claras e orientativas em caso de falhas ou buscas sem retorno. | Cliente | O cliente assume que o sistema está quebrado, sem saber como corrigir os filtros ou tentar novamente. |

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade?**
Sim. Mesmo que o LocalEats entregue todas as telas e botões prometidos (como a busca e a consulta de pedidos), o excesso de lentidão ao carregar restaurantes (necessidade implícita de desempenho) inviabiliza o uso prático. A qualidade do produto depende da satisfação global do usuário; se o sistema funciona, mas é lento ou inseguro, ele falha em entregar valor real ao negócio e ao cliente.

---

### Tarefa 2: Exploração da aplicação

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
| :--- | :--- | :--- | :--- | :--- |
| Breno Prado dos Santos | Filtrar restaurantes | Aplicada busca por especialidade válida e, em seguida, por termo inexistente sem correspondência. | No filtro válido, a lista exibiu apenas restaurantes correspondentes. No termo inexistente, a lista ficou vazia com aviso amigável na tela. | `evidencias/seu-nome-filtrar-restaurantes.png` |

---

### Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
| :--- | :--- | :--- | :--- | :--- |
| Breno Prado dos Santos | Ao aplicar um filtro de pesquisa que não retorne resultados, o sistema deve apresentar uma mensagem explicativa e um meio rápido de redefinir os filtros. | Usabilidade / Proteção contra erros de usuário | Garante que o cliente compreenda o resultado nulo e consiga ajustar a busca de forma intuitiva, mantendo uma boa experiência de navegação no LocalEats. | Testar filtros com combinações inválidas e verificar visualmente a exibição da mensagem de alerta e a funcionalidade do botão de redefinição. |

---

## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini Notebook.

**Como foi utilizada:**
Auxílio na estruturação do documento, formulação das necessidades explícitas e implícitas do LocalEats e definição do requisito de qualidade ISO/IEC 25000.

**Como as respostas foram verificadas:**
O conteúdo gerado foi revisado e testado diretamente na aplicação LocalEats para garantir conformidade com os requisitos da disciplina e acurácia dos dados.