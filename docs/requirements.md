# TechStore

- Versão: 0.1

- Status: Levantamento de requisitos (em andamento)

## Objetivo

- Sistema de e-commerce para venda e gerenciamento de produtos eletrônicos, permitindo o controle de clientes, pedidos, pagamentos e estoque, além da integração com as operações da loja física.

## Escopo

- Controlar usuários, produtos, categorias, estoque, carrinho, pedidos, pagamentos, endereços e devoluções.

## Usuários

- Proprietário
- Funcionário
- Cliente

## Requisitos Funcionais

- RF01: Cadastrar produtos.
- RF02: Editar produtos.
- RF03: Inativar produtos.
- RF04: Permitir que clientes realizem pedidos.
- RF05: Permitir cancelamento de pedidos conforme regras de negócios.
- RF06: Editar estoque.
- RF07: Consultar pedidos.
- RF08: Consultar produtos.
- RF09: Acesso com login e senha.
- RF10: Cliente pode adicionar produtos ao carrinho.
- RF11: Cliente pode acompanhar o status do pedido.
- RF12: O sistema deve registrar o pagamento de pedidos.
- RF13: Cliente pode solicitar aviso de disponibilidade de produtos sem estoque.

## Requisitos Não Funcionais

- RNF01: O sistema deve possuir autenticação segura.
- RNF02: O sistema deve armazenar senhas de forma criptografada.
- RNF03: O sistema deve possuir backup dos dados.
- RNF04: O sistema deve responder às requisições em até 2 segundos em condições normais de uso.

## Regras de Negócio

- RN01: Somente o proprietário pode inativar produtos.
- RN02: Funcionários não podem cancelar pedidos realizados por clientes sem autorização do proprietário.
- RN03: Clientes podem criar pedidos através do sistema.
- RN04: Funcionários podem gerenciar pedidos realizados.
- RN05: Funcionários podem alterar estoque.
- RN06: Quando um produto possuir menos de 5 unidades em estoque, o sistema deverá gerar um aviso de estoque baixo.
- RN07: Apenas usuários autenticados podem acessar o sistema.
- RN08: Ao criar um pedido, os produtos devem ser reservados até a confirmação ou cancelamento do pagamento.
- RN09: Pedidos cancelados não podem voltar ao fluxo de envio.
- RN10: Clientes devem possuir cadastro no sistema para realizar pedidos.
- RN11: Usuários não autenticados podem consultar produtos, mas devem estar autenticados para realizar pedidos.
- RN12: Um pedido não pode possuir mais de um pagamento confirmado.
- RN13: Após a confirmação do pagamento, o sistema deve remover a reserva dos produtos e atualizar o estoque com a venda realizada.
- RN14: Após a confirmação do pagamento, o pedido deve ser alterado automaticamente para EM_PREPARACAO.
- RN15: Pedidos podem ser cancelados até o momento do envio.
- RN16: Clientes podem solicitar devolução de produtos dentro do prazo estabelecido após o recebimento do pedido.
- RN17: Pedidos enviados não podem ser cancelados, apenas devolvidos conforme política de devolução.
- RN18: Solicitações de devolução dentro dos critérios definidos podem ser aprovadas automaticamente pelo sistema.
- RN19: Solicitações de devolução fora dos critérios automáticos devem ser analisadas por um funcionário.
- RN20: Produtos sem estoque devem permanecer disponíveis para consulta, porém não podem ser adicionados ao carrinho.

## Entidades

- Usuário
- Produto
- Categoria
- Carrinho
- Pedido
- ItemPedido
- Pagamento
- Endereço
- Estoque
- Devolução

## Dúvidas

- Como será feita a confirmação de pagamento?
- O sistema terá integração com gateway de pagamento?
- Produtos podem possuir mais de uma categoria?
- Cliente pode comprar sem cadastro?
- Pedido pode ser alterado após pagamento?
- Como funciona o cancelamento de pedidos?
- Como será realizado o cálculo do valor total do pedido?

## Decisões Técnicas Pendentes

- Tecnologia do backend.
- Banco de dados utilizado.
- Forma de autenticação.
- Estratégia de deploy.
