# Produto

## Descrição

Representa um produto eletrônico comercializado pela TechStore.

Um produto pode ser cadastrado por funcionários como rascunho e posteriormente aprovado pelo proprietário para ficar disponível para venda.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do produto |
| codigo | string | Sim | Código interno gerado automaticamente pelo sistema |
| nome | string | Sim | Nome comercial do produto |
| descricao | string | Sim | Descrição detalhada do produto |
| fabricante | string | Sim | Fabricante do produto |
| modelo | string | Sim | Modelo do produto |
| preco | decimal | Sim | Valor de venda do produto |
| peso | decimal | Não | Peso do produto |
| garantia | integer | Não | Tempo de garantia em meses |
| status | enum | Sim | RASCUNHO, ATIVO ou INATIVO |

## Regras de Negócio Relacionadas

- RN21: Produtos cadastrados por funcionários devem ser criados com status RASCUNHO.
- RN22: Produtos em status RASCUNHO não podem ser exibidos aos clientes.
- RN23: Somente o proprietário pode aprovar um produto para venda.
- RN24: Somente produtos com status ATIVO podem ser vendidos.
- RN25: Produtos podem possuir múltiplas imagens.
- RN27: O código interno do produto deve ser gerado automaticamente pelo sistema.
- RN28: Produtos podem ser salvos como rascunho antes da aprovação.
- RN29: Apenas produtos completos podem ser aprovados para venda.
- RN30: Produtos inativados podem ser reativados pelo proprietário.

## Relacionamentos

- Um produto pode possuir várias categorias.
- Um produto possui um estoque.
- Um produto pode possuir várias imagens.
- Um produto pode possuir várias especificações técnicas.
- Um produto pode estar presente em vários pedidos através da entidade ItemPedido.

## Observações

Produtos sem estoque permanecem disponíveis para consulta, porém não podem ser adicionados ao carrinho ou vendidos.
