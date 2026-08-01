# Carrinho

## Descrição

Representa os produtos selecionados pelo cliente antes da criação de um pedido.

O carrinho permite que o cliente escolha produtos, altere quantidades e prossiga para a finalização da compra.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do carrinho |
| clienteId | UUID | Sim | Cliente responsável pelo carrinho |
| status | enum | Sim | ATIVO, ABANDONADO ou CONVERTIDO |
| criadoEm | datetime | Sim | Data de criação do carrinho |

## Regras de Negócio Relacionadas

- RN03: Clientes podem criar pedidos através do sistema.
- RN08: Ao criar um pedido, os produtos devem ser reservados até a confirmação ou cancelamento do pagamento.
- RN20: Produtos sem estoque não podem ser adicionados ao carrinho.
- RN26: Produtos sem estoque não podem ser vendidos.

## Relacionamentos

- Um cliente pode possuir vários carrinhos.
- Um carrinho possui vários itens através da entidade ItemCarrinho.
- Um carrinho pode ser convertido em um pedido.

## Observações

O carrinho representa uma intenção de compra e não uma venda realizada.

A reserva de estoque ocorre somente no momento da criação do pedido, após a finalização da compra.

## Exemplo:

- Carrinho:
Teclado Mecânico x1
Mouse Gamer x2

Após finalizar:

Carrinho → Pedido
