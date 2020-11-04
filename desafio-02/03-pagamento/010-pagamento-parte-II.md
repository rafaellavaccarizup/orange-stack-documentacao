# Pagamento - Parte II

## Necessidades

No fluxo de [pagamento](005-pagamento-parte-I.md) recebemos os dados da transação, porém, o serviço de **issuer** do 
banco que é responsável por **autorizar** a transação em si.
                                                  
Temos uma API específica para autorização da transação, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**

Infelizmente o sistema **issuer** somente entende as informações do cartão em texto aberto, portanto, será necessário fazer 
o fluxo de [detokenização](../02-token/030-detokenizacao.md) antes.

## Restrições

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo