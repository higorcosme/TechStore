# Casos de Uso - TechStore

## UC01 - Realizar Pedido

### Ator Principal:

- Cliente.

### Objetivo:

- Permitir que o cliente realize a compra de produtos disponíveis no sistema.

### Pré-condições:

- Cliente deve possuir cadastro no sistema.
- Cliente deve estar autenticado.
- Produto deve existir.
- Produto deve possuir quantidade disponível para reserva.

### Fluxo principal:

1. Cliente adiciona produtos ao carrinho.
2. Cliente inicia finalização do pedido.
3. Cliente informa ou confirma endereço de entrega.
4. Sistema valida estoque disponível.
5. Sistema reserva os produtos.
6. Sistema cria o pedido.
7. Sistema define status AGUARDANDO_PAGAMENTO.

### Fluxos alternativos:

- Caso o produto não possua estoque disponível, o sistema deverá informar ao cliente que o produto está indisponível e impedir a criação do pedido.
- Caso o cliente não possua endereço cadastrado, o sistema deverá solicitar o preenchimento do endereço antes da finalização do pedido.
- Caso o cliente cancele o pedido, o sistema deverá remover a reserva dos produtos e atualizar o status do pedido para CANCELADO.

## Status do Pedido

- AGUARDANDO_PAGAMENTO.
- PAGAMENTO_CONFIRMADO.
- EM_PREPARACAO.
- ENVIADO.
- RECEBIDO.
- CANCELADO.

## Status do Pagamento

- AGUARDANDO.
- APROVADO.
- RECUSADO.
- CANCELADO.
