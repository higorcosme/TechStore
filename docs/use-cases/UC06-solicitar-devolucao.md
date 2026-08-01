# Casos de Uso - TechStore

## UC06 - Solicitar Devolução

### Ator Principal

- Cliente

### Atores Secundários

- Funcionário

### Objetivo

Permitir que o cliente solicite a devolução de um pedido recebido.

### Pré-condições

- Cliente autenticado.
- Pedido recebido.
- Pedido dentro do prazo de devolução.

### Fluxo Principal

1. Cliente acessa seus pedidos.
2. Cliente solicita devolução.
3. Sistema registra a solicitação.
4. Sistema verifica os critérios automáticos.
5. Caso aprovado automaticamente, o sistema autoriza a devolução.
6. Caso contrário, encaminha para análise de um funcionário.

### Fluxos Alternativos

- Pedido fora do prazo.
- Pedido inexistente.
- Pedido ainda não recebido.
- Solicitação já existente para o mesmo pedido.
