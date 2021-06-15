# Deployment do serviços: Uma abordagem ops

> Antes de começar a fazer as atividades de deploy, volte para o [conteúdo teórico para aprender a utilizar as tecnologias](https://github.com/zup-academy/nosso-cartao-documentacao/blob/master/orange-talent-4/README.md#deploy) e tirar o máximo de proveito das atividades. 

Neste desafio, o esperado é que o resultado de seus builds, sejam imagens docker e artefatos aptos a serem "deployados" em um cluster
kubernetes.

neste caso, usando Amazon EKS. O diagrama abaixo pode ajudar a ilustrar o cenário proposto:

![diagrama desafio deployment](../../recursos/diagramas/diagrama_desafio_deploy.png)

*Não se preocupe com a infraestrutura, todo o ambiente está pronto e aguardando o seu projeto =)*

## Necessidades

O artefato do build de seu projeto é uma imagem docker, por isso, é necessário criar o arquivo Dockerfile para conteinerizar sua app.


## Informações de suporte

- Dúvidas em como criar um Dockerfile [Esse link](https://github.com/docker/labs/tree/master/developer-tools/java/) tem uma explicação sobre como você pode fazer isso.


## Como nós implementamos

Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://youtu.be/5VvZbL4fGcI) você verá como foi o passo que seguimos para realizar essa tarefa.
