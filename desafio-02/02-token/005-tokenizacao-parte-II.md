# Tokenização Parte II

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) recebemos os dados do cartão, porém, precisamos adicionar algumas 
verificações de segurança, tais como:
 
- Qual canal (parceiro) foi feito a solicitação de [tokenização](005-tokenizacao-parte-I.md)

- Os dados do cartão foram criptografados com a chave do(a) [parceiro(a)](../01-parceiro/005-cricao-parceiro.md)
   
## Restrições

Devemos receber os seguintes dados:

- Identificador do(a) parceiro(a) deve ser obrigatório e ser um(a) parceiro(a) existente e ativo(a).

Devemos verificar os seguintes dados:

- Nome do(a) portador(a) do cartão deve ser criptografado com a chave RSA pública do(a) parceiro(a)
- CPF do(a) portador(a) do cartão deve ser criptografado com a chave RSA pública do(a) parceiro(a)
- Número do cartão deve ser criptografado com a chave RSA pública do(a) parceiro(a)
- Data de expiração do cartão no formato MMYY deve-ser criptografado com a chave RSA pública do(a) parceiro(a)
- Código de verificação (CVV) do cartão deve-ser criptografado com a chave RSA pública do(a) parceiro(a)

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o token deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo