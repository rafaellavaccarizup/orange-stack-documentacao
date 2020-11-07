# Pagamento - Parte II

## Necessidades

No fluxo de [pagamento](005-pagamento-parte-I.md) recebemos os dados da transação, porém, o serviço de **issuer** do 
banco que é responsável por **autorizar** a transação em si.
                                                  
Temos uma API específica para autorização da transação, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**

Infelizmente o sistema **issuer** somente entende as informações do cartão em texto aberto, portanto, será necessário fazer 
o fluxo de [detokenização](../02-token/030-detokenizacao.md) antes.

## Restrições

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

No fluxo de [pagamento](005-pagamento-parte-I.md) recebemos os dados da transação, porém, o serviço de **issuer** do 
banco que é responsável por **autorizar** a transação em si.

- Caso a devolutiva for **APROVADO** devemos seguir com o fluxo de [pagamento](005-pagamento-parte-I.md)

- Caso a devolutiva **não** for **APROVADO** devemos retornar um erro específico:
                                                                        
    - Retornar **HTTP Status 422** quando o pagamento **não** for **APROVADO**

## Informações de suporte

## Sugestões de busca de conteúdo