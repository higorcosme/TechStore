# Estoque

## Descrição

Representa o controle de quantidade disponível dos produtos comercializados pela TechStore.

O estoque é responsável por controlar quantidades disponíveis, produtos reservados em pedidos aguardando pagamento e alertas de baixa quantidade.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do estoque |
| produtoId | UUID | Sim | Produto relacionado ao estoque |
| quantidadeDisponivel | integer | Sim | Quantidade disponível para venda |
| quantidadeReservada | integer | Sim | Quantidade reservada em pedidos aguardando pagamento |
| estoqueMinimo | integer | Sim | Quantidade mínima para gerar alerta de estoque baixo |

## Regras de Negócio Relacionadas

- RN06: Quando um produto possuir menos de 5 unidades em estoque, o sistema deverá gerar um aviso de estoque baixo.
- RN08: Ao criar um pedido, os produtos devem ser reservados até a confirmação ou cancelamento do pagamento.
- RN13: Após a confirmação do pagamento, o sistema deve remover a reserva dos produtos e atualizar o estoque com a venda realizada.
- RN20: Produtos sem estoque devem permanecer disponíveis para consulta, porém não podem ser adicionados ao carrinho.
- RN26: Produtos sem estoque não podem ser vendidos.

## Relacionamentos

- Um estoque pertence a um produto.
- Um produto possui um único controle de estoque.

## Observações

A quantidade reservada não representa uma venda concluída. Ela representa produtos temporariamente bloqueados para pedidos que aguardam confirmação de pagamento.
