# Tokenização - Parte III

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) recebemos os dados do cartão e do(a) parceiro(a), porém, precisamos 
verificar se o cartão é válido no **issuer**.

Temos uma API específica para verificar se o cartão é válido, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**
   
## Restrições

Devemos fornecer os seguintes dados:

- Nome do(a) portador(a) do cartão

- CPF do(a) portador(a) do cartão

- Número do cartão

- Data de expiração do cartão no formato MMYY

- Código de verificação (CVV) do cartão

## Resultado Esperado

No processo de [tokenização](005-tokenizacao-parte-I.md) devemos considerar o status recebido da verificação de cartão 
retornada pelo **issuer**.

- Caso a devolutiva do estado do cartão for **ATIVO** devemos seguir com o fluxo de [tokenização](005-tokenizacao-parte-I.md)

- Caso a devolutiva do estado do contrato **não** for **ATIVO** devemos retornar um erro específico:
                                                                        
    - Retornar **HTTP Status 422** quando o cartão **não** for **ATIVO**

## Informações de suporte

## Sugestões de busca de conteúdo