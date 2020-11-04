# Tokenização - Parte IV

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) recebemos os dados do cartão e do(a) parceiro(a), porém, precisamos 
enviar **assincronamente** para o sistema de **fraude** analisar tal ação. 
   
## Restrições

Devemos fornecer os seguintes dados:

- Identificador do token

- A hora e data em UTC da geração do token

- URL da [API de Lifecycle](020-token-lifecycle.md), caso seja identificado uma fraude será chamado essa API para bloquear o Token.

- Método HTTP da [API de Lifecycle](020-token-lifecycle.md)

## Resultado Esperado

- Em caso de sucesso, o token deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo