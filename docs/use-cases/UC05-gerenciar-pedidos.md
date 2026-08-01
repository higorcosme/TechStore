# Casos de Uso - TechStore

## UC05 - Gerenciar Pedidos

### Atores Principais

- Funcionário
- Proprietário

### Objetivo

Permitir o acompanhamento do ciclo de vida dos pedidos.

### Pré-condições

- Usuário autenticado.
- Pedido existente.

### Fluxo Principal

1. Usuário consulta um pedido.
2. Sistema apresenta o status atual.
3. Usuário atualiza o status conforme a etapa da venda.
4. Sistema registra a alteração.

### Fluxos Alternativos

- Pedido inexistente.
- Tentativa de alterar um pedido cancelado.
- Tentativa de alterar um pedido já concluído.
- Tentativa de cancelar pedido após envio.
