# Tokenização - Parte III

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) recebemos os dados do cartão e do(a) parceiro(a), porém, precisamos 
verificar se o cartão é válido no **issuer**.

Temos uma API específica para verificar se o cartão é válido, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**
   
## Restrições

Devemos fornecer os seguintes dados:

- Nome do(a) portador(a) do cartão em texto aberto.

- CPF do(a) portador(a) do cartão em texto aberto.

- Número do cartão em texto aberto.

- Data de expiração do cartão no formato MMYY em texto aberto.

- Código de verificação (CVV) do cartão em texto aberto.

## Resultado Esperado

- Em caso de sucesso, o token deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo