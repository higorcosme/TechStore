# Casos de Uso - TechStore

## UC02 - Processar Pagamento

### Ator principal:

- Cliente

### Atores secundários:

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
