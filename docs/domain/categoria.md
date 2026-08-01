# Categoria

## Descrição

Representa a classificação dos produtos vendidos pela TechStore.

As categorias permitem organizar os produtos para facilitar a navegação e consulta dos clientes no sistema.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único da categoria |
| nome | string | Sim | Nome da categoria |
| descricao | string | Não | Descrição da categoria |
| status | enum | Sim | ATIVA ou INATIVA |

## Regras de Negócio Relacionadas

- Produtos podem possuir múltiplas categorias.
- Categorias inativas não devem ser utilizadas para novos produtos.

## Relacionamentos

- Uma categoria pode possuir vários produtos.
- Um produto pode possuir várias categorias através da entidade ProdutoCategoria.

## Exemplos

Categoria:

- Placas de Vídeo
Produtos relacionados:
RTX 4060
RTX 4070
RX 7800
