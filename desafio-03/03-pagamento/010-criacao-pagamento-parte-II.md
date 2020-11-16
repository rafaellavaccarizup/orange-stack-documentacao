# Criação de um pagamento - Parte II

## Necessidades

No processo de [criação de pagamento](005-criacao-pagamento-parte-I.md) é preciso verificar se o **acquirer** aprova ou 
não o pagamento em si.

Temos uma API específica para autorizar o pagamento ou não, vamos analisá-la?

**[gRPC - Protobuf](../../recursos/protobuf/acquirer.proto)**
    
## Resultado Esperado

No processo de [criação de pagamento](005-criacao-pagamento-parte-I.md) devemos considerar o status recebido do **acquirer**:

- Caso a devolutiva do status for **APPROVED** devemos seguir com o fluxo de [criação de pagamento](005-criacao-pagamento-parte-I.md)

- Caso a devolutiva do status **não** for **APPROVED** devemos retornar um erro **HTTP Status 422** específico:

## Informações de suporte

## Sugestões de busca de conteúdo