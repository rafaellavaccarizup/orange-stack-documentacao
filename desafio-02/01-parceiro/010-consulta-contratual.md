# Consulta de situação contratual

## Necessidades

No processo de **criação de parceiro** é preciso consultar o **issuer** com o objetivo de verificar se o seu contrato 
se encontra **ativo**.

Temos uma API específica para consultar o status contratual do parceiro, vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()** 
    
## Restrições

- O documento do parceiro deve ser fornecido.

## Resultado Esperado

No processo de [crição de parceiro](005-cricao-parceiro.md) devemos considerar o status recebido da consulta de situação 
contratual retornada pelo **issuer**.

- Caso a devolutiva do estado for **ATIVO** o parceiro deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Caso a devolutiva do estado **não** for **ATIVO** devemos cancelar a requisição de cadastramento de parceiro.

## Informações de suporte

## Sugestões de busca de conteúdo