# Casos de Uso - TechStore

## UC01 - Realizar Pedido

### Ator principal:

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

## UC02 - Processar Pagamento

### Ator Principal:

- Cliente

### Atores Secundários:

- Gateway de pagamento

### Objetivo:

- Permitir que o cliente realize o pagamento de um pedido criado no sistema.

### Pré-condições:

- Pedido deve existir.
- Pedido deve possuir status AGUARDANDO_PAGAMENTO.
- Pedido não pode estar cancelado.

### Fluxo principal:

1. Cliente inicia o pagamento do pedido.
2. Sistema envia a solicitação de pagamento para o gateway.
3. Gateway processa o pagamento.
4. Gateway retorna confirmação do pagamento.
5. Sistema confirma o pagamento.
6. Sistema remove a reserva dos produtos.
7. Sistema atualiza o estoque dos produtos vendidos.
8. Sistema altera o status do pagamento para APROVADO.
9. Sistema altera o status do pedido para EM_PREPARACAO.

### Fluxos alternativos:

- Caso o pagamento seja recusado pelo gateway, o sistema deverá atualizar o status do pagamento para RECUSADO e manter o pedido aguardando pagamento.

- Caso o cliente abandone o processo de pagamento, o pedido deverá permanecer com status AGUARDANDO_PAGAMENTO.

- Caso o gateway de pagamento esteja indisponível, o pagamento deverá permanecer com status AGUARDANDO.

- Caso a confirmação do pagamento demore, o pedido deverá permanecer com status AGUARDANDO até receber retorno do gateway.

- Caso o cliente tente realizar múltiplos pagamentos simultâneos para o mesmo pedido, o sistema deverá impedir pagamentos duplicados.
