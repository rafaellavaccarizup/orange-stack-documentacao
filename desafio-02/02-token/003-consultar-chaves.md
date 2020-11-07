# Obter chave RSA pública

## Necessidades

Precisamos criar uma **API REST** que devolva a chave RSA pública dado o(a) parceiro(a), assim os sistemas conseguem 
criptografar as informações sensíveis (cartão, pessoal, etc.) e integrar com as APIs do serviço de token.

## Restrições

Devemos receber os seguintes dados:

- Identificador do(a) parceiro(a)

Devemos retornar as seguintes informações:

- Chave pública RSA do(a) parceiro(a)

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - A chave pública deve ser retornada no **body**
    
    - Retornar **HTTP Status 200**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 404** quando o(a) parceiro(a) não for encontrado
    
    - Retornar **HTTP Status 422** quando o(a) parceiro(a) não estivar ativo(a)
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo