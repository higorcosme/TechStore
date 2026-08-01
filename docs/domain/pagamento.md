# Pagamento

## Descrição

Representa uma tentativa de pagamento realizada para um pedido da TechStore.

O pagamento é processado através de um gateway de pagamento externo, responsável por aprovar ou recusar a transação.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do pagamento |
| pedidoId | UUID | Sim | Pedido relacionado ao pagamento |
| status | enum | Sim | AGUARDANDO, APROVADO, RECUSADO ou CANCELADO |
| metodo | enum | Sim | CARTAO, PIX ou BOLETO |
| valor | decimal | Sim | Valor da tentativa de pagamento |
| realizadoEm | datetime | Não | Data da aprovação do pagamento |

## Regras de Negócio Relacionadas

- RN12: Um pedido não pode possuir mais de um pagamento confirmado.
- RN13: Após a confirmação do pagamento, o sistema deve remover a reserva dos produtos e atualizar o estoque com a venda realizada.
- RN14: Após a confirmação do pagamento, o pedido deve ser alterado automaticamente para EM_PREPARACAO.

## Status do Pagamento

### AGUARDANDO

Pagamento iniciado, porém aguardando resposta do gateway.

### APROVADO

Pagamento confirmado pelo gateway.

### RECUSADO

Pagamento negado pelo gateway.

### CANCELADO

Pagamento cancelado pelo cliente ou pelo sistema.

## Relacionamentos

- Um pedido pode possuir várias tentativas de pagamento.
- Apenas um pagamento pode possuir status APROVADO por pedido.

## Observações

Um pedido pode possuir múltiplas tentativas de pagamento.

## Exemplo:

Pedido 001

Pagamento 1:

Cartão
RECUSADO

Pagamento 2:

Pix
APROVADO

Após a aprovação do pagamento:


Pagamento:
AGUARDANDO

↓

APROVADO

↓

Pedido:
AGUARDANDO_PAGAMENTO

↓

EM_PREPARACAO
