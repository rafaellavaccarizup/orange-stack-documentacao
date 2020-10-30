# Criação de um produto

## Contexto

Cada terminal pode suportar um determinado conjunto de produtos. Está informação deve estar 
cadastrada no terminal, para isso precisamos cadastrar os produtos (Cartão Itaucard 2.0 - Modalidade Crédito)
nos terminais. 

Está tarefa deve ser realizada depois do cadastro de produtos.

## Objetivo

Realizar a associação de um ou mais produtos ao terminal, permitindo que um terminal seja capaz de realizar transações de um ou mais produtos
produto.

## Necessidades

A associação deve conter as seguintes informações:

- Identificador do terminal
- Identificador do produto
- Data de inclusão da associação

## Restrições

- Identificador do terminal deve ser obrigatório
- Identificador do produto deve ser obrigatório
- Terminal deve estar registrado e ativo no sistema
- Produto deve estar registrado e ativo no sistema
- Devemos seguir as boas práticas de integração utilizada

## Resultado Esperado

- Em caso de sucesso, o terminal deve estar apto a realizar transações do(s) produto(s).
- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo
