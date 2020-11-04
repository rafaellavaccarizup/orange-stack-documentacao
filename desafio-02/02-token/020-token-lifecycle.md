# Token Lifecycle

## Necessidades

No fluxo de [tokenização](005-tokenizacao-parte-I.md) criamos o token, porém, o banco precisa gerenciar o mesmo, portanto 
será necessário a criação de uma **API REST** para poder **Ativar**, **Suspender** e **Bloquear** um determinado Token.

Como o banco e o sistema de **fraude** irá interagir com essa **API REST**, será necessário seguir o contrato estabelecido.

**Contrato**

- **Método HTTP:** Deve ser o PATCH.
- **URL:** Deve receber o identificador do token, como por exemplo: /tokens/{tokenId}
- **Headers:** Não deve possuir.
- **Body:** Deve ser passado os seguintes campos:
    - **status** no tipo String podendo ser os seguintes valores:
        - ACTIVE
        - SUSPENDED
        - BLOCKED

## Restrições

Devemos efetuar as seguintes validações:

- Uma vez que o token se encontra no status **ACTIVE** somente é possível alterar para **SUSPENDED** ou **BLOCKED**

- Uma vez que o token se encontra no status **SUSPENDED** somente é possível alterar para **ACTIVE** ou **BLOCKED**

- Uma vez que o token se encontra no status **BLOCKED** não é possível alterar para **ACTIVE** ou **SUSPENDED**

Devemos efetuar as seguintes alterações:

- No fluxo de [tokenização](005-tokenizacao-parte-I.md) o token deve ser criado com o status **ACTIVE**.

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.


## Resultado Esperado

- Em caso de sucesso, o status do token deve ser alterado no sistema.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo