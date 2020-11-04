# Detokenização

## Necessidades

Precisamos desenvolver uma funcionalidade **interna** de **detokenização** que recebe um determinado token e devolve 
os dados do cartão.

## Restrições

Devemos receber os seguintes dados:

- Identificador do token deve ser obrigatório.

- Identificador do(a) parceiro(a) deve ser obrigatório e ser um(a) parceiro(a) existente e ativo(a).

Devemos efetuar as seguintes validações:

- Token deve pertencer ao parceiro(a) fornecido

Devemos retornar os seguintes dados:

- Nome do(a) portador(a) do cartão em texto aberto.

- CPF do(a) portador(a) do cartão em texto aberto.

- Número do cartão em texto aberto.

- Data de expiração do cartão no formato MMYY em texto aberto.

- Código de verificação (CVV) do cartão em texto aberto.

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, os dados do cartão devem ser retornados em texto aberto.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo