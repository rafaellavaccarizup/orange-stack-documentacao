## Luram

#### [Localstack](https://github.com/localstack/localstack)

1ª Precisamos rodar o docker-compose

```yaml
version: '2.1'

services:
  localstack:
    container_name: localstack
    image: localstack/localstack:0.12.1
    network_mode: bridge
    ports:
      - "4566:4566"
      - "4571:4571"
    environment:
      - SERVICES=dynamodb
      - DEBUG=${DEBUG- }
      - DATA_DIR=${DATA_DIR- }
      - DOCKER_HOST=unix:///var/run/docker.sock
    volumes:
      - "${TMPDIR:-/tmp/localstack}:/tmp/localstack"
      - "/var/run/docker.sock:/var/run/docker.sock"
```

2º Precisamos configurar nosso [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

```shell script
$ aws configure --profile default

AWS Access Key ID: test
AWS Secret Access Key: test
Default region name [us-east-1]: us-east-1
```

Para testar se a configuração está ok, execute o comando abaixo:

```shell script
$ aws --endpoint-url=http://localhost:4566 dynamodb list-tables
```

3º [Opcional] Precisamos instalar o [LocalStack AWS CLI](https://github.com/localstack/awscli-local)

Para testar a instalação, execute o comando abaixo:

```shell script
$ awslocal dynamodb list-tables
```

#### [AWS](https://micronaut-projects.github.io/micronaut-aws/latest/guide/#introduction)

É preciso adicionar a dependência do SDK V2:

```
implementation platform("com.amazonaws:aws-java-sdk-bom:1.11.894")
```

É preciso configurar as credencias da AWS no `application.yaml`:

```yaml
aws:
  accessKeyId: ${AWS_KEY_ID:test}
  secretKey: ${AWS_SECRET_ID:test}
  region: ${AWS_REGION:us-east-1}
```

#### [DynamoDB](https://micronaut-projects.github.io/micronaut-aws/latest/guide/#dynamodb)

É preciso configurar o SDK V2 da AWS e adicionar a dependência do SDK do DynamoDB:

```
implementation("com.amazonaws:aws-java-sdk-dynamodb")
```

Para configurar sua entity iremos utilizar o [DynamodbMapper](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBMapper.Methods.html) e suas [Anotações do Dynamodb](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBMapper.Annotations.html)

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

#### [Exception Handler](https://docs.micronaut.io/latest/guide/index.html#errorHandling)

#### [gRPC - Micronaut](https://micronaut-projects.github.io/micronaut-grpc/snapshot/guide/index.html)

#### [gRPC - OpenTracing](https://docs.micronaut.io/latest/guide/index.html#distributedTracing)

Precisamos adicionar as seguintes dependências

```
implementation("io.micronaut:micronaut-tracing")
runtime("io.opentracing.contrib:opentracing-grpc:0.2.3")
compile("io.jaegertracing:jaeger-thrift:0.31.0")
```

Precisamos adicionar as seguintes properties:

```yaml
tracing:
  jaeger:
    enabled: ${JAEGER_ENABLED:true}
    sampler:
      probability: ${JAEGER_SAMPLE:1}
    sender:
      agentHost: ${JAEGER_HOST:localhost}
      agentPort: ${JAEGER_PORT:5775}
    reporter:
      flushInterval: 2000
      maxQueueSize: 200
```

#### [PostgreSQL - Micronaut](https://docs.micronaut.io/latest/guide/index.html#dataAccess)

**build.gradle**

```groovy
// JPA \ Hibernate
annotationProcessor("io.micronaut.data:micronaut-data-processor")
runtime("io.micronaut.sql:micronaut-jdbc-hikari")
implementation("io.micronaut.data:micronaut-data-jdbc")
compileOnly("jakarta.persistence:jakarta.persistence-api:2.2.2")
// PostgreSQL
runtime("org.postgresql:postgresql")
```

**application.yml**

```yaml
# PostgreSQL
datasources:
  default:
    url: ${JDBC_URL:`jdbc:postgresql://localhost:5432/partner`}
    username: ${JDBC_USER:postgres}
    password: ${JDBC_PASSWORD:postgres}
    driverClassName: ${JDBC_DRIVER:org.postgresql.Driver}
```