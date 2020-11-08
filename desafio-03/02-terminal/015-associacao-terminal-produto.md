# Associação de Produto no Terminal

## Contexto

Cada terminal pode suportar um determinado conjunto de produtos. Está informação deve estar cadastrada no terminal, 
para isso precisamos cadastrar os produtos (Cartão Itaucard 2.0 - Modalidade Crédito) nos terminais. 

## Objetivo

Realizar a associação de um ou mais produtos ao terminal, permitindo que um terminal seja capaz de realizar transações 
de um ou mais produtos.

## Necessidades

A associação deve conter as seguintes informações:

- Identificador do terminal na URL

- Identificador do produto na URL

- Data e hora da inclusão da associação no formato UTC

## Restrições

- Identificador do terminal deve ser obrigatório

- Identificador do produto deve ser obrigatório

- Data e hora da inclusão deve ser registrada pelo sistema no formato UTC

- Terminal deve estar registrado e ativo no sistema

- Produto deve estar registrado e ativo no sistema

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

   - O Terminal deve estar apto a realizar transações do(s) produto(s)

   - Deve ser retornado o **HTTP Status 201**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 404** quando não encontrado o produto ou terminal
    
    - Retornar **HTTP Status 422** quando o produto ou terminal não estiver ativo
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo