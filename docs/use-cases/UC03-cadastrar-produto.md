# Casos de Uso - TechStore

## UC03 - Cadastrar Produto

### Atores Principais

- Proprietário
- Funcionário

### Objetivo

Permitir o cadastro de um novo produto no sistema.

### Pré-condições

- Usuário autenticado.
- Usuário possuir permissão para cadastrar produtos.

### Fluxo Principal

1. Usuário acessa o cadastro de produtos.
2. Usuário informa os dados do produto.
3. Sistema gera automaticamente o código interno do produto.
4. Caso o usuário seja Funcionário, o produto é salvo com status RASCUNHO.
5. Caso o usuário seja Proprietário, o produto pode ser salvo como ATIVO.
6. Sistema registra o produto.

### Fluxos Alternativos

- Caso existam campos obrigatórios não preenchidos, o sistema deverá impedir o cadastro.
- Caso um funcionário tente publicar um produto, o sistema deverá impedir a operação.
- Caso o proprietário aprove um produto em rascunho, o sistema deverá alterar seu status para ATIVO.

### Status do Produto

- RASCUNHO
- ATIVO
- INATIVO
