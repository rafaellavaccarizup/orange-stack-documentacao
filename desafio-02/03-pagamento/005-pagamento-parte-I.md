# Pagamento - Parte I

## Necessidades

Precisamos desenvolver uma funcionalidade de **pagamento** que recebe o parceiro, token e informações da transação.

## Restrições

Devemos receber os seguintes dados:

- Identificador do token deve ser obrigatório e ser existente e [ativo](../02-token/020-token-lifecycle.md).

- Identificador do(a) parceiro(a) deve ser obrigatório e ser um(a) parceiro(a) existente e ativo(a).

- CNPJ do estabelecimento deve ser obrigatório

- Valor deve ser obrigatório e maior que zero.

Devemos armazenar os seguintes dados:

- Todos os dados que recebemos na requisição

- A hora e data em UTC da operação

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo