# Criação de Parceiro(a) - Parte I

## Necessidades

Precisamos cadastrar os parceiros(as) do banco que podem fazer uso do sistema de [Tokenização](../README.md).
   
## Restrições

Devemos receber os seguintes dados do parceiro(a):

- Nome do(a) Parceiro(a) deve ser obrigatório.

- CNPJ deve ser obrigatório, válido e único.

- Tipo de Canal deve ser obrigatório.
    - NFC: Near-field communication    
    - ECM: Ecommerce       
    - MOB: Mobile

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - O(A) novo(a) parceiro(a) deve ser armazenado(a) no sistema, com um identificador gerado pelo sistema não sequencial
    
    - Retornar **HTTP Status 201** com Header Location preenchido com a URL do(a) novo(a) parceiro(a)
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 400** quando violado alguma das restrições
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo