# Relacionamentos do Domínio - TechStore

Este documento apresenta os principais relacionamentos entre as entidades do domínio da TechStore.

---

# Usuário e Cliente

## Relacionamento


Usuário 1 : 1 Cliente


## Descrição

Um usuário do tipo CLIENTE possui um perfil de cliente associado.

Exemplo:


Usuário

Nome
Email
Senha
Tipo: CLIENTE

↓

Cliente

Dados relacionados às compras

---

# Cliente e Endereço

## Relacionamento


Cliente 1 : N Endereço


## Descrição

Um cliente pode possuir vários endereços cadastrados.

Exemplo:


Cliente

Casa
Trabalho
Outro endereço

---

# Cliente e Carrinho

## Relacionamento


Cliente 1 : N Carrinho


## Descrição

Um cliente pode possuir vários carrinhos ao longo do tempo.

O carrinho pode possuir os seguintes estados:

- ATIVO
- ABANDONADO
- CONVERTIDO

---

# Carrinho e ItemCarrinho

## Relacionamento


Carrinho 1 : N ItemCarrinho


## Descrição

Um carrinho possui vários produtos selecionados pelo cliente.

---

# Produto e Categoria

## Relacionamento


Produto N : N Categoria


## Entidade intermediária:


ProdutoCategoria


## Descrição

Um produto pode pertencer a várias categorias e uma categoria pode possuir vários produtos.

Exemplo:


Produto:

Notebook Gamer

Categorias:

Notebook
Gamer
Informática

---

# Produto e Estoque

## Relacionamento


Produto 1 : 1 Estoque


## Descrição

Cada produto possui um controle de estoque responsável por:

- quantidade disponível;
- quantidade reservada;
- estoque mínimo.

---

# Produto e Imagem

## Relacionamento


Produto 1 : N ImagemProduto


## Descrição

Um produto pode possuir várias imagens para exibição aos clientes.

---

# Produto e Especificação

## Relacionamento


Produto 1 : N EspecificacaoProduto


## Descrição

Um produto pode possuir diversas características técnicas.

Exemplo:


Produto:

Notebook

Especificações:

Processador:
Intel i7

Memória:
16GB RAM


---

# Cliente e Pedido

## Relacionamento


Cliente 1 : N Pedido


## Descrição

Um cliente pode realizar vários pedidos.

---

# Pedido e ItemPedido

## Relacionamento


Pedido 1 : N ItemPedido


## Descrição

Um pedido possui os produtos comprados pelo cliente.

---

# Produto e ItemPedido

## Relacionamento


Produto 1 : N ItemPedido


## Descrição

Um produto pode aparecer em vários pedidos diferentes.

---

# Pedido e Pagamento

## Relacionamento


Pedido 1 : N Pagamento


## Descrição

Um pedido pode possuir várias tentativas de pagamento.

Regra:


Apenas um pagamento pode possuir status APROVADO.


---

# Pedido e Devolução

## Relacionamento


Pedido 1 : 0..1 Devolução


## Descrição

Um pedido pode possuir uma solicitação de devolução.

---

# Visão Geral

Representação simplificada:


Usuário
|
|
Cliente
|
+------ Endereço
|
+------ Carrinho
| |
| |
| ItemCarrinho
| |
| |
| Produto
|
+------ Pedido
|
+------ ItemPedido
|
+------ Pagamento
|
+------ Devolução

Produto
|
+------ Estoque
|
+------ ImagemProduto
|
+------ EspecificacaoProduto
|
+------ Categoria


---

# Observações

Este modelo representa a primeira versão do domínio da TechStore.

Antes da implementação, o modelo deve passar por validação com:

- Diagrama de domínio.
- Modelo de banco de dados.
- Definição da arquitetura do sistema.
