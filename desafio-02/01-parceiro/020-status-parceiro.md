# Alterar status do(a) Parceiro(a)

## Necessidades

O banco precisa desativar os parceiros(as) que utilizam o sistema de [Tokenização](../README.md) de forma errada ou devido 
problemas contratuais.

Caso o parceiro(a) resolva os seus problemas contratuais o banco pode reativar o mesmo.
    
## Restrições

- Identificador do(a) parceiro(a) é obrigatório na URL

- Na [criação do parceiro(a)](005-cricao-parceiro-parte-I.md) devemos criar como ativado(a).

- Na [consulta de parceiro(a)](015-consulta-parceiro.md) devemos informar o status do(a) mesmo(a).

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - Deve ser alterado o status do(a) parceiro(a)
    
    - Deve ser retornado o **HTTP Status 200**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 404** quando não encontrado o terminal
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo