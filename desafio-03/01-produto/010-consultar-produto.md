# Consultar Produto

## Objetivo

Possibilitar que um usuário ou outro sistema consulte os dados de um determinado produto.

## Necessidades

- Realizar a consulta de um determinado produto

## Restrições

- Identificador do produto é obrigatório na URL

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - Deve ser retornado os dados do produto
    
    - Deve ser retornado o **HTTP Status 200**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 404** quando não encontrado o produto
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo