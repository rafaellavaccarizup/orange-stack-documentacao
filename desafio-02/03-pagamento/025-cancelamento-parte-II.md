# Cancelamento - Parte II

## Necessidades

No fluxo de [cancelamento](020-cancelamento-parte-I.md) recebemos os dados do token, parceiro e o identificador da transação 
de pagamento, porém, o serviço de **issuer** do banco que é responsável por **autorizar** o cancelamento em si.
                                                  
Temos uma API específica para o cancelamento da transação, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**

Infelizmente o sistema **issuer** somente entende as informações do cartão em texto aberto, portanto, será necessário 
fazer o fluxo de [detokenização](../02-token/030-detokenizacao.md) antes.

## Restrições

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

No fluxo de [cancelamento](020-cancelamento-parte-I.md) recebemos os dados do token, parceiro e o identificador da transação 
de pagamento, porém, o serviço de **issuer** do banco que é responsável por **autorizar** o cancelamento em si.

- Caso a devolutiva for **APROVADO**:

    - Devemos seguir com o fluxo de [cancelamento](020-cancelamento-parte-I.md)
    - O pagamento deve ser armazenado no sistema com status **CANCELADO**
    - O cancelamento deve ser armazenado no sistema com status **APROVADO**

- Caso a devolutiva **não** for **APROVADO** devemos retornar um erro específico:
                                                                        
    - Retornar **HTTP Status 422** quando o cancelamento **não** for **APROVADO**
    
## Informações de suporte

## Sugestões de busca de conteúdo