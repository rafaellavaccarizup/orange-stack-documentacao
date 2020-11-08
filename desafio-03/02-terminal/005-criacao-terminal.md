# Criação de Terminal

## Contexto

Terminal é uma representação de uma maquininha de cartão presente em estabelecimentos comerciais.

## Objetivo

Realizar a criação de um terminal no sistema.

## Necessidades

- Número de série do terminal

- Fabricante do terminal (Rede, Cielo, Stone, etc.)

- CNPJ do estabelecimento

- Nome do estabelecimento

- Endereço do estabelecimento

## Restrições

- Número de série do terminal deve ser obrigatório e único

- Fabricante do terminal deve ser obrigatório

- CNPJ do estabelecimento deve ser obrigatório e válido

- Nome do estabelecimento deve ser obrigatrio

- Endereço do estabelecimento, contendo logradouro, cep, complemento, cidade, estado e país

**Lembre-se**

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:

    - O novo terminal deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial
    
    - O novo terminal deve estar com status "ativo" no sistema
    
    - Retornar **HTTP Status 201** com Header Location preenchido com a URL do novo terminal
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 400** quando violado alguma das restrições
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado

## Informações de suporte

## Sugestões de busca de conteúdo
