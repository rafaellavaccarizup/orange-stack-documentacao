# Pagamento - Parte III

## Necessidades

No fluxo de [pagamento](005-pagamento-parte-I.md) recebemos os dados da transação, porém, precisamos 
enviar **assincronamente** para o sistema de **fraude** analisar tal ação.

**Informações do Kafka** - FIXME LURAM

- Tópico
- Contrato da mensagem 
   
## Restrições

Devemos fornecer os seguintes dados:

- Identificador da transação

- A hora e data em UTC da geração do token

- CNPJ do estabelecimento deve ser obrigatório

- Valor deve ser obrigatório e maior que zero.

## Resultado Esperado

- Em caso de sucesso, o pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo