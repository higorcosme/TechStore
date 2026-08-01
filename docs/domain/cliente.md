# Cliente

## Descrição

Representa um cliente da TechStore que realiza compras através do sistema.

O cliente está associado a um usuário e possui informações necessárias para realizar pedidos, acompanhar compras e solicitar devoluções.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do cliente |
| usuarioId | UUID | Sim | Usuário relacionado ao cliente |

## Regras de Negócio Relacionadas

- RN03: Clientes podem criar pedidos através do sistema.
- RN10: Clientes devem possuir cadastro no sistema para realizar pedidos.
- RN11: Usuários não autenticados podem consultar produtos, mas devem estar autenticados para realizar pedidos.
- RN16: Clientes podem solicitar devolução de produtos dentro do prazo estabelecido após o recebimento do pedido.
- RN18: Solicitações de devolução dentro dos critérios definidos podem ser aprovadas automaticamente pelo sistema.
- RN19: Solicitações de devolução fora dos critérios automáticos devem ser analisadas por um funcionário.

## Relacionamentos

- Um cliente pertence a um usuário.
- Um cliente pode possuir vários endereços.
- Um cliente pode possuir vários carrinhos.
- Um cliente pode possuir vários pedidos.
- Um cliente pode solicitar devoluções através de seus pedidos.

## Observações

O cliente representa apenas informações específicas relacionadas à compra. Dados de autenticação e acesso ao sistema pertencem à entidade Usuário.
