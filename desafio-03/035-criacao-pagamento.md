# Criação de um pagamento

## Contexto

Precisamos de uma API que seja capaz de receber requisições de pagamento, essa API vai atender
terminais POS (maquininha) que se encontra nos estabelecimentos.
Essa API deve ser síncrona de maneira que o cliente tenha resposta no momento
da compra.


## Objetivo

Realizar a criação de uma API Rest para receber requisições de transações financeiras

## Necessidades

A Requisição de transações deve conter as seguintes informações
- Token do cartão (que nesse caso foi previamente criado)
- Identificador do terminal
- Identificador do produto
- Valor da Transação
- Data/Hora da transação no Terminal

## Restrições

- Token do cartão (que nesse caso foi previamente criado) obrigatório
- Identificador do terminal obrigatório
- Identificador do produto obrigatório
- Valor da Transação obrigatório
- Data/Hora da transação no Terminal obrigatório

## Resultado Esperado

- A proposta deve estar armazenada no sistema, com um identificador gerado pelo sistema.
- Retornar **201** com Header Location preenchido com a URL da nova proposta em caso de sucesso.
- Retornar **400** quando violado alguma das restrições.

## Informações de suporte

## Sugestões de busca de conteúdo
