# Endereço

## Descrição

Representa os endereços utilizados pelo cliente para entrega dos pedidos realizados na TechStore.

Um cliente pode possuir mais de um endereço cadastrado, permitindo escolher o endereço desejado durante a finalização da compra.

## Atributos

| Atributo | Tipo | Obrigatório | Descrição |
|---|---|:---:|---|
| id | UUID | Sim | Identificador único do endereço |
| clienteId | UUID | Sim | Cliente relacionado ao endereço |
| rua | string | Sim | Logradouro |
| numero | string | Sim | Número do endereço |
| complemento | string | Não | Complemento do endereço |
| bairro | string | Sim | Bairro |
| cidade | string | Sim | Cidade |
| estado | string | Sim | Estado |
| cep | string | Sim | Código postal |

## Regras de Negócio Relacionadas

- Um cliente deve possuir endereço cadastrado para concluir um pedido.
- O endereço utilizado no pedido deve ser armazenado para manter o histórico da compra.

## Relacionamentos

- Um cliente pode possuir vários endereços.
- Um pedido utiliza um endereço de entrega.

## Observações

O endereço deve ser associado ao pedido no momento da criação para evitar alterações futuras no histórico da compra.

## Exemplo:

- Cliente possui:

Endereço residencial
Endereço comercial

Pedido 001:
Entrega no endereço residencial
