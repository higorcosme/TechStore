# Devolução

## Descrição

Representa uma solicitação de devolução realizada pelo cliente após o recebimento de um pedido.

A devolução permite que o cliente solicite o retorno de um produto conforme a política definida pela TechStore.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único da devolução |
| pedidoId | UUID | Sim | Pedido relacionado à devolução |
| motivo | string | Sim | Motivo informado pelo cliente |
| status | enum | Sim | SOLICITADA, APROVADA ou RECUSADA |
| criadoEm | datetime | Sim | Data da solicitação |

## Regras de Negócio Relacionadas

- RN16: Clientes podem solicitar devolução de produtos dentro do prazo estabelecido após o recebimento do pedido.
- RN17: Pedidos enviados não podem ser cancelados, apenas devolvidos conforme política de devolução.
- RN18: Solicitações de devolução dentro dos critérios definidos podem ser aprovadas automaticamente pelo sistema.
- RN19: Solicitações de devolução fora dos critérios automáticos devem ser analisadas por um funcionário.

## Status da Devolução

### SOLICITADA

Cliente realizou uma solicitação de devolução que ainda está aguardando análise.

### APROVADA

Solicitação aceita pelo sistema ou funcionário.

### RECUSADA

Solicitação negada por não atender aos critérios definidos.

## Relacionamentos

- Um pedido pode possuir uma devolução.
- Uma devolução pertence a um pedido.

## Observações

A devolução não representa um cancelamento do pedido.

## O fluxo ocorre após o recebimento do produto:

Pedido recebido

↓

Cliente solicita devolução

↓

Análise da solicitação

↓

Aprovada ou recusada


Caso aprovada:

- Produto retorna conforme regras de estoque.
- Pagamento pode ser estornado conforme política definida.
