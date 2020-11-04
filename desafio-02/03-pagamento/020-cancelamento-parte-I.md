# Cancelamento - Parte I

## Necessidades

Precisamos desenvolver uma funcionalidade de **cancelamento** que recebe o token, parceiro e o identificador da transação 
de pagamento com o objetivo de cancelar a mesma.

## Restrições

Devemos receber os seguintes dados:

- Identificador do token deve ser obrigatório e ser existente e [ativo](../02-token/020-token-lifecycle.md).

- Identificador do(a) parceiro(a) deve ser obrigatório e ser um(a) parceiro(a) existente e [ativo(a)](../01-parceiro/020-status-parceiro.md).

- Identificador da transação de pagamento.

Devemos efetuar as seguintes validações:

- A transação de pagamento deve ser do mesmo token e parceiro

- A transação de pagamento deve estar no status **APROVADA**

Devemos armazenar os seguintes dados:

- Todos os dados que recebemos na requisição

- A hora e data em UTC da operação

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo