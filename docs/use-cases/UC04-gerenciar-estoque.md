# Casos de Uso - TechStore

## UC04 - Gerenciar Estoque

### Atores Principais

- Funcionário
- Proprietário

### Objetivo

Permitir o controle da quantidade disponível dos produtos.

### Pré-condições

- Usuário autenticado.
- Produto existente.

### Fluxo Principal

1. Usuário localiza o produto.
2. Usuário informa a quantidade de entrada ou saída.
3. Sistema atualiza o estoque.
4. Sistema verifica se o estoque ficou abaixo do mínimo.
5. Caso necessário, o sistema gera aviso de estoque baixo.

### Fluxos Alternativos

- Produto inexistente.
- Quantidade inválida.
- Operação que resulte em estoque negativo deve ser impedida.
