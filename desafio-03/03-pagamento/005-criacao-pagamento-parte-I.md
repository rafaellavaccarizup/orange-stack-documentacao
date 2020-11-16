# Criação de um pagamento - Parte I

## Contexto

Precisamos de uma API que seja capaz de receber requisições de pagamento, essa API vai atender terminais POS (maquininha) 
que se encontra nos estabelecimentos.

Essa API deve ser síncrona de maneira que o cliente tenha resposta no momento da compra.

## Objetivo

Realizar a criação de uma API REST para receber requisições de transações financeiras.

## Necessidades

A Requisição de transações deve conter as seguintes informações:

- Token do Cartão (que nesse caso foi previamente criado)

- Identificador do Terminal

- Identificador do Produto

- Valor da Transação

- Data e hora da transação no Terminal no formato ISO 8601 (yyyy-MM-dd'T'HH:mm:ssZ)

## Restrições

- Token do Cartão (que nesse caso foi previamente criado) deve ser obrigatório

- Identificador do Terminal deve ser obrigatório

- Identificador do Produto deve ser obrigatório

- Valor da Transação deve ser obrigatório e positivo

- Data e hora da transação no Terminal dever obrigatório e no formato UTC

- Terminal deve estar registrado e ativo no sistema

- Produto deve estar registrado e ativo no sistema

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

# Importante! Nossa API REST precisa seguir o seguinte **[contrato](../../recursos/open-api/openapi-desafio-03.yaml)**

## Resultado Esperado

- Em caso de sucesso:

    - O novo pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial
    
    - Retornar **HTTP Status 201** com Header Location preenchido com a URL do novo pagamento
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 422**
        
        - Quando não for encontrado o produto
        
        - Quando não for encontrado o terminal
        
        - Quando o produto não for ativo
        
        - Quando o terminal não for ativo
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo