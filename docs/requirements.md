# TechStore

- Versão: 0.1

- Status: Levantamento de requisitos (em andamento)

## Objetivo

- Sistema para gerenciar produtos, estoque e pedidos de uma loja de produtos eletrônicos, facilitando o controle das vendas e do estoque.

## Escopo

- Controlar usuários, produtos, estoque, clientes e pedidos.

## Usuários

- Proprietário
- Funcionário

## Requisitos Funcionais

- RF01: Cadastrar produtos.
- RF02: Editar produtos.
- RF03: Excluir produtos.
- RF04: Cadastrar pedidos.
- RF05: Excluir pedidos.
- RF06: Editar estoque.
- RF07: Consultar pedidos.
- RF08: Consultar produtos.
- RF09: Acesso com login e senha.

## Requisitos Não Funcionais

## Regras de Negócio

- RN01: Somente proprietário pode excluir produtos.
- RN02: Somente o proprietário pode excluir pedidos.
- RN03: Funcionários podem cadastrar pedidos.
- RN04: Funcionários podem alterar estoque.
- RN05: Quando um produto possuir menos de 5 unidades em estoque, o sistema deverá gerar um aviso de estoque baixo.
- RN06: Apenas usuários autenticados podem acessar o sistema.
- RN07: O sistema deve impedir a criação de pedidos quando a quantidade solicitada de um produto for maior que o estoque disponível.
- RN08: Um pedido deve possuir um status que representa sua etapa atual no processo de venda.
- RN09: Todo pedido criado deve iniciar com o status AGUARDANDO_PAGAMENTO.

## Entidades

- Usuário
- Cliente
- Pedido
- Produto
- ItemPedido

## Dúvidas

- Um produto pode ser editado?
- Um pedido pode ser editado após ser criado?

## Pendências Técnicas

- Sistema web?
- Segurança do sistema?
- Tempo máximo de resposta?
- Backups?
