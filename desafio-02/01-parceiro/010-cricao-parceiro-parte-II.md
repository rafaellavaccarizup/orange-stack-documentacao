# Criação de Parceiro(a) - Parte II

## Necessidades

No processo de [criação de parceiro(a)](005-cricao-parceiro-parte-I.md) é preciso consultar o **issuer** com o objetivo de 
verificar se o seu contrato encontra-se **ativo**.

Temos uma API específica para consultar o status contratual do parceiro(a), vamos analisá-la?

**[SWAGGER OU PROTOBUF - FIXME LURAM]()**
    
## Restrições

- O documento do parceiro(a) deve ser fornecido.

## Resultado Esperado

No processo de [crição de parceiro(a)](005-cricao-parceiro-parte-I.md) devemos considerar o status recebido da consulta de situação 
contratual retornada pelo **issuer**.

- Caso a devolutiva do estado for **ATIVO** o parceiro(a) deve ser armazenado(a) no sistema, com um identificador 
gerado pelo sistema não sequencial.

- Caso a devolutiva do estado **não** for **ATIVO** devemos cancelar a requisição de cadastramento de parceiro(a).

## Informações de suporte

## Sugestões de busca de conteúdo