# Criação de um terminal

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

- Número de série do terminal deve ser obrigatório
- Fabricante do terminal deve ser obrigatório
- CNPJ do estabelecimento deve ser obrigatório e válido
- Nome do estabelecimento deve ser obrigatrio
- Endereço do estabelecimento, contendo logradouro, cep, complemento, cidade, estado e país
- Caso sucesso o terminal deve estar com status = "ativo"

## Resultado Esperado

- Em caso de sucesso, o novo terminal deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.
- Em caso de erro, deve ser retornado os erros específicos.
- Devemos seguir as boas práticas de REST em ambos os cenários.

## Informações de suporte

## Sugestões de busca de conteúdo
