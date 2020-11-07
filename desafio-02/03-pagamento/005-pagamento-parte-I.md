# Pagamento - Parte I

## Necessidades

Precisamos desenvolver uma funcionalidade de **pagamento** que recebe o parceiro, token e informações da transação.

## Restrições

Devemos receber os seguintes dados:

- Identificador do token deve ser obrigatório e ser existente e [ativo](../02-token/025-token-lifecycle.md).

- Identificador do(a) parceiro(a) deve ser obrigatório e ser um(a) parceiro(a) existente e [ativo(a)](../01-parceiro/020-status-parceiro.md).

- CNPJ do estabelecimento deve ser obrigatório

- Valor deve ser obrigatório e maior que zero.

- Tipo de Canal deve ser obrigatório e suportado pelo(a) parceiro(a)
    - NFC: Near-field communication    
    - ECM: Ecommerce       
    - MOB: Mobile

Devemos armazenar os seguintes dados:

- Todos os dados que recebemos na requisição

- A hora e data em UTC da operação

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - O pagamento deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial
    
    - Retornar **HTTP Status 201** com Header Location preenchido com a URL do novo pagamento
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 400** quando violado algum tipo ou conteúdo recebido
    
    - Retornar **HTTP Status 422** quando violado alguma regra de negócio
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo