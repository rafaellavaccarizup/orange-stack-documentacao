# Cancelamento - Parte III

## Necessidades

No fluxo de [cancelamento](020-cancelamento-parte-I.md) recebemos os dados do token, parceiro e o identificador da transação 
de pagamento, porém, precisamos enviar **assincronamente** para o sistema de **fraude** analisar tal ação.

**Informações do Kafka** - FIXME LURAM

- Tópico
- Contrato da mensagem 
   
## Restrições

Devemos fornecer os seguintes dados:

- Identificador da transação de cancelamento

- A hora e data em UTC da transação

- CNPJ do estabelecimento deve ser obrigatório

- Valor deve ser obrigatório e maior que zero.

## Resultado Esperado

- Em caso de sucesso:
    - O cancelamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.
    - O pagamento deve ser armazenado no sistema com status **CANCELADO**

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo