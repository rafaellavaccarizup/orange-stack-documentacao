# Token Lifecycle

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) criamos o token, porém, o banco ou sistema de fraude precisa 
gerenciar o mesmo, portanto, será necessário receber esses eventos via [Apache Kafka](https://kafka.apache.org/)

**Informações do Kafka** - FIXME LURAM

- Tópico
- Contrato da mensagem 

## Restrições

Devemos efetuar as seguintes validações:

- Uma vez que o token se encontra no status **ACTIVE** somente é possível alterar para **SUSPENDED** ou **BLOCKED**

- Uma vez que o token se encontra no status **SUSPENDED** somente é possível alterar para **ACTIVE** ou **BLOCKED**

- Uma vez que o token se encontra no status **BLOCKED** não é possível alterar para **ACTIVE** ou **SUSPENDED**

Devemos efetuar as seguintes alterações:

- No fluxo de [tokenização](005-tokenizacao-parte-I.md) o token deve ser criado com o status **ACTIVE**.

**Lembre-se** 

Devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o status do token deve ser alterado no sistema.

- Em caso de violação das retrições a mesma deve ser logada sem a interrupção do consumo dos próximos eventos no [Apache Kafka](https://kafka.apache.org/)

## Informações de suporte

## Sugestões de busca de conteúdo