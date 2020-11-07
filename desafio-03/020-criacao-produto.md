# Criação de Produto

## Contexto

Produto é um tipo de cartão (Débito, Crédito, etc.) que tem algumas informações como emissor do cartão, nome do produto 
e modalidade nas quais são utilizadas pelo terminal para saber deve proseguir ou não com a transação de compra ou 
estorno\cancelamento.

## Objetivo

Realizar a criação de um produto.

## Necessidades

O Produto tem as seguintes informações:

- Nome do Emissor (Instituição Financeira)

- Nome do Produto (Itaucard 2.0)

- Modalidade (crédito/débito)

## Restrições

- Nome do emissor deve ser obrigatório

- Nome do Produto deve ser obrigatório

- Modalidade (crédito/débito) deve ser obrigatória

- Devemos seguir as boas práticas de integração utilizada

## Resultado Esperado

- Em caso de sucesso:

    - O novo produto deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial
    
    - Retornar **HTTP Status 201** com Header Location preenchido com a URL do novo produto
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 400** quando violado alguma das restrições
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo