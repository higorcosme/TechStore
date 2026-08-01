# Usuário

## Descrição

Representa qualquer pessoa que possui acesso ao sistema TechStore.

O usuário é a entidade responsável pela autenticação e definição das permissões de acesso conforme seu tipo.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do usuário |
| nome | string | Sim | Nome completo do usuário |
| email | string | Sim | Email utilizado para acesso ao sistema |
| senha | string | Sim | Senha armazenada de forma criptografada |
| tipo | enum | Sim | CLIENTE, FUNCIONÁRIO ou PROPRIETÁRIO |
| status | enum | Sim | ATIVO ou INATIVO |

## Regras de Negócio Relacionadas

- RN01: Somente o proprietário pode inativar produtos.
- RN02: Funcionários não podem cancelar pedidos realizados por clientes sem autorização do proprietário.
- RN04: Funcionários podem gerenciar pedidos realizados.
- RN05: Funcionários podem alterar estoque.
- RN07: Apenas usuários autenticados podem acessar o sistema.
- RN10: Clientes devem possuir cadastro no sistema para realizar pedidos.
- RN11: Usuários não autenticados podem consultar produtos, mas devem estar autenticados para realizar pedidos.

## Relacionamentos

- Um usuário pode possuir um perfil de cliente.
- Um usuário possui permissões conforme seu tipo.

## Observações

Os tipos de usuário definem as permissões dentro do sistema:

### CLIENTE

Pode:

- Consultar produtos.
- Gerenciar carrinho.
- Realizar pedidos.
- Acompanhar pedidos.
- Solicitar devoluções.

### FUNCIONÁRIO

Pode:

- Cadastrar produtos.
- Gerenciar pedidos.
- Alterar estoque.

### PROPRIETÁRIO

Pode:

- Aprovar produtos.
- Inativar produtos.
- Reativar produtos.
- Autorizar operações restritas.
