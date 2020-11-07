# Criação de Chaves

## Necessidades

Precisamos adicionar uma camada de segurança para interagir com as APIs do serviço de token, portanto, precisamos criar 
uma **API REST** que gere uma chave RSA pública e privada dado o(a) parceiro(a).  

## Restrições

Devemos receber os seguintes dados:

- Identificador do(a) parceiro(a)

Devemos efetuar as seguintes validações:

- Parceiro(a) deve existir no sistema

- Parceiro(a) deve estar ativo(a) no sistema

- Caso já tenha um conjunto de chave pública e privada RSA, devemos remover as mesmas e considerar as novas

Devemos retornar as seguintes informações:

- Chave pública RSA do(a) parceiro(a)

**Importante**

Internamente devemos armazenar e gerar a chave pública e privada RSA

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - A chave pública e privada RSA deve ser armazenada no sistema
    
    - Retornar **HTTP Status 201**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 400** quando violado alguma das restrições
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo