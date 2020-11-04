# Criação de Parceiro(a)

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
    
- Chave RSA privada deve ser obrigatória.

- Chave RSA pública deve ser obrigatória.

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o(a) parceiro(a) deve ser armazenado(a) no sistema, com um identificador gerado pelo sistema 
não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo