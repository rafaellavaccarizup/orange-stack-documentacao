# Expondo para o frontend: Detalhamento de uma chave Pix

## Necessidades

Agora precisamos permitir que o frontend consulte uma chave Pix para que nosso usuário consiga ver os detalhes da sua chave. Basicamente, o que iremos fazer é expor em nossa API REST a [operação de consulta de uma chave Pix](020-consultando-os-dados-de-uma-chave-pix.md).
   
## Restrições

Para esta funcionalidade, precisamos somente consultar uma chave Pix pelo **Pix ID** e **identificador do cliente**. Para isso, você pode levantar essas informações com detalhes a partir da [atividade de consulta de chave Pix que implementamos no módulo Key-Manager gRPC](020-consultando-os-dados-de-uma-chave-pix.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

## Resultado Esperado

- Em caso de sucesso, deve-se retornar os dados da chave Pix encontrada;

- Em caso de chave não encontrada, deve-se retornar status de erro `404-NOT_FOUND` com uma mensagem amigável para o usuário;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte
- Quer saber como retornar um objeto em formato JSON com o Micronaut? [Esse vídeo](https://www.youtube.com/watch?v=PML9YWZUnbk&feature=youtu.be) tem uma explicação sobre como você pode fazer isso
- Quer saber como você pode escrever queries com o Micronaut? [Neste vídeo](https://www.youtube.com/watch?v=cph_Ei7tulY&feature=youtu.be) é mostrada como criar métodos nos repositórios que são mapeados para queries

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=eDeDklLdvAE&feature=youtu.be) você vai ver como foi o passo que seguimos para realizar essa tarefa
