# Tokenização - Parte IV

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) recebemos os dados do cartão e do(a) parceiro(a), porém, precisamos 
enviar **assincronamente** para o sistema de **fraude** analisar tal ação.

**Informações do Kafka** - FIXME LURAM

- Tópico
- Contrato da mensagem 
   
## Restrições

Devemos fornecer os seguintes dados:

- Identificador do token

- A hora e data em UTC da geração do token

## Resultado Esperado

- Em caso de sucesso, o token deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo
