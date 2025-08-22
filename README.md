### 6. Sistema de Controle de Estoque
**Descrição:** Sistema para monitorar estoque de produtos.

**Requisitos Funcionais:**
1. Cadastro de produtos.
2. Entrada e saída de estoque.
3. Alertas de baixo estoque.
4. Relatórios.

**Requisitos Não Funcionais:**
- Performance alta.
- Exportação para Excel.

**Histórias de Usuário:**
- **Como gerente**, quero visualizar relatórios **para que** eu possa tomar decisões.
  - **Critérios de Aceite:** Relatório exportável; atualização em tempo real.

**Etapas/Sprints:**
- Sprint 1: CRUD de produtos.
- Sprint 2: Movimentações.
- Sprint 3: Relatórios.

**Entidades:**

-   **Produto**
    -   `id` (PK)\
    -   `nome` (obrigatório)\
    -   `codigo` (único, até 20 caracteres)\
    -   `quantidade` (inteiro ≥ 0)
-   **Movimentacao**
    -   `id` (PK)\
    -   `produto_id` (FK → Produto)\
    -   `tipo` (enum: `ENTRADA` ou `SAIDA`)\
    -   `quantidade` (inteiro \> 0)\
    -   `data`\
    -   **Regra:** Se `SAIDA`, não permitir
        `quantidade > estoque atual`.
