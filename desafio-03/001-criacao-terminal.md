# Criação de um terminal

## Contexto

Terminal é uma representação de uma maquininha de cartão presente em estabelecimentos comerciais.

## Objetivo

Realizar a criação de um terminal no sistema.

## Necessidades

- O documento necessário para identificar o dono do terminal deve ser CPF/CNPJ
- número de série do terminal 
- fabricante do terminal 
- estabelecimento que o terminal foi alocado 
- endereço do estabelecimento

## Restrições

- documento do solicitante deve ser obrigatório e válido
- número de série do terminal obrigatório
- fabricante do terminal obrigatório
- estabelecimento que o terminal foi alocado obrigatório 
- endereço do estabelecimento, contendo logradouro, cep, complemento, cidade, estado e país
- ao final do cadastro o terminal deve estar com status = "ativo"

## Resultado Esperado

- O novo terminal deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

## Informações de suporte

## Sugestões de busca de conteúdo

## ----------------------

## Luram

#### [Bean Validation](https://docs.micronaut.io/1.2.6/guide/index.html#beanValidation)

É preciso adicionar a anotação `@Introspected` conforme exemplo:

```kotlin
@Introspected
data class CreateTerminalRequest(
        @field:NotBlank var document: String? =  null,
        @field:NotBlank var serial: String? =  null,
        @field:NotBlank var manufacturer: String? =  null,
        @field:NotBlank var merchant: String? =  null,
        @field:NotBlank var merchantAddress: String? =  null
)
```

É preciso anotar a classe com a anotação `@Validated`, conforme exemplo:

```kotlin
@Validated
class TerminalController() {

}
```

É preciso anotar o parâmetro do método com a anotação `@Valid`, conforme exemplo:


```kotlin
fun post(@Valid request: CreateTerminalRequest) {

}
```

#### [Bean Validation - Custom Constraint](https://docs.micronaut.io/1.2.6/guide/index.html#_defining_additional_constraints)