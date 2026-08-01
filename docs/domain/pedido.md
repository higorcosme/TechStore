# Pedido

## Descrição

Representa uma compra realizada por um cliente através do sistema TechStore.

O pedido contém os produtos adquiridos, informações de entrega, pagamento e acompanha todas as etapas do processo de venda.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do pedido |
| clienteId | UUID | Sim | Cliente responsável pelo pedido |
| enderecoId | UUID | Sim | Endereço utilizado para entrega |
| status | enum | Sim | AGUARDANDO_PAGAMENTO, EM_PREPARACAO, ENVIADO, RECEBIDO, FINALIZADO ou CANCELADO |
| valorTotal | decimal | Sim | Valor total da compra |
| criadoEm | datetime | Sim | Data de criação do pedido |

## Regras de Negócio Relacionadas

- RN03: Clientes podem criar pedidos através do sistema.
- RN08: Ao criar um pedido, os produtos devem ser reservados até a confirmação ou cancelamento do pagamento.
- RN09: Pedidos cancelados não podem voltar ao fluxo de envio.
- RN12: Um pedido não pode possuir mais de um pagamento confirmado.
- RN13: Após a confirmação do pagamento, o sistema deve remover a reserva dos produtos e atualizar o estoque com a venda realizada.
- RN14: Após a confirmação do pagamento, o pedido deve ser alterado automaticamente para EM_PREPARACAO.
- RN15: Pedidos podem ser cancelados até o momento do envio.
- RN17: Pedidos enviados não podem ser cancelados, apenas devolvidos conforme política de devolução.

## Status do Pedido

### AGUARDANDO_PAGAMENTO

Pedido criado, porém aguardando confirmação do pagamento.

### EM_PREPARACAO

Pagamento confirmado e pedido em processo de separação e preparação para envio.

### ENVIADO

Pedido enviado ao cliente.

### RECEBIDO

Cliente confirmou recebimento do pedido.

### FINALIZADO

Processo de compra concluído.

### CANCELADO

Pedido cancelado antes do envio.

## Relacionamentos

- Um cliente pode possuir vários pedidos.
- Um pedido possui vários itens através da entidade ItemPedido.
- Um pedido pode possuir vários pagamentos.
- Um pedido pode possuir uma devolução.
- Um pedido utiliza um endereço de entrega.

## Observações

O pedido é criado somente após o cliente finalizar a compra.

## Fluxo esperado:

Carrinho

↓

Pedido criado

↓

AGUARDANDO_PAGAMENTO

↓

Pagamento aprovado

↓

EM_PREPARACAO

↓

ENVIADO

↓

RECEBIDO

↓

FINALIZADO
