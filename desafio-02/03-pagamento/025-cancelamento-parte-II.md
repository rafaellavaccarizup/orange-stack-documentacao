# Cancelamento - Parte II

## Necessidades

No fluxo de [cancelamento](020-cancelamento-parte-I.md) recebemos os dados do token, parceiro e o identificador da transação 
de pagamento, porém, o serviço de **issuer** do banco que é responsável por **autorizar** o cancelamento em si.
                                                  
Temos uma API específica para o cancelamento da transação, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**

Infelizmente o sistema **issuer** somente entende as informações do cartão em texto aberto, portanto, será necessário 
fazer o fluxo de [detokenização](../02-token/030-detokenizacao.md) antes.

## Restrições

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Caso a devolutiva do cancelamento for **APROVADA**:
    - O cancelamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.
    - O pagamento deve ser armazenado no sistema com status **CANCELADO**
        
- Caso a devolutiva do cancelamento **não** for **APROVADA** devemos cancelar a requisição de cancelamento.

## Informações de suporte

## Sugestões de busca de conteúdo