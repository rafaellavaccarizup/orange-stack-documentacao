# Deployment do serviços: Uma abordagem ops

O codebuild precisa de um arquivo de configuração com instruções para construir o build. Nesse ponto o esperado é um arquivo
de build em /pipeline/buildspec.yaml

Segue um exemplo válido de buildspec.yaml para este cenário:

```yml
version: 0.2

phases:
  install:
    commands:
      - curl -o /bin/kubectl https://storage.googleapis.com/kubernetes-release/release/v1.16.0/bin/linux/amd64/kubectl
      - curl -sS -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.10.3/2018-07-26/bin/linux/amd64/aws-iam-authenticator
      - wget -qO- https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz | tar xvz
      - mv linux-amd64/helm /bin/helm
      - chmod +x /bin/kubectl /bin/helm ./aws-iam-authenticator
      - export PATH=$PWD/:$PATH
      - apt-get update && apt-get -y install jq python3-pip python3-dev && pip3 install --upgrade awscli

  pre_build:
    commands:
      - echo connecting ecr
      - docker login -u AWS -p $(aws ecr-public get-login-password --region us-east-1) $URL_REPO
      # aqui você poderá colocar os comandos para o build de seu projeto, exemplo:
      - sh gradlew build
      - echo exporting kubeconfig
      - export KUBECONFIG=$HOME/.kube/config
      
  build:
    commands:
      - echo Build started on `date`
      - echo Building the Docker image...  
      - docker build -t $DEPLOYMENT_NAME . 
      - docker tag $DEPLOYMENT_NAME:$IMAGE_TAG $URL_REPO/$DEPLOYMENT_NAME:$IMAGE_TAG
      - echo Build completed on `date`  

  post_build:
    commands:
      - echo Pushing in to Amazon ECR...
      - docker push $URL_REPO/$DEPLOYMENT_NAME:$IMAGE_TAG
      - echo Push completed on `date`  
      - echo deploying to cluster...
      # aqui um exemplo de implementação utilizando helm, caso utilize manifestos, lembre-se do kubectl apply -f <ARQUIVO>.yaml
      - helm version --short
      - helm lint pipeline/helm/$DEPLOYMENT_NAME --values pipeline/helm/$DEPLOYMENT_NAME/values.yaml
      - aws eks update-kubeconfig --name $EKS_CLUSTER_NAME --role-arn $ARN_ROLE
      - kubectl get nodes
      - helm upgrade -i $DEPLOYMENT_NAME pipeline/helm/$DEPLOYMENT_NAME/ --values pipeline/helm/$DEPLOYMENT_NAME/values.yaml
```
OBS: Atente-se a linha em pre_build: 

```yml
- sh gradlew build
```

e em post_build

```yml
- helm upgrade -i $DEPLOYMENT_NAME pipeline/helm/$DEPLOYMENT_NAME/ --values pipeline/helm/$DEPLOYMENT_NAME/values.yaml
```

Ajuste-as de acordo com seu processo de build e deploy (kubectl ou helm)


## Informações de suporte

- Caso queira relembrar sobre o funcionamento do codebuild, os links abaixo podem ajudar.


[Codebuild: O que é?](https://youtu.be/ESetAFRhn5M)

[Codebuild: Buildspec.yaml](https://youtu.be/8JXAwykjp-Q)

[Codebuild: Criando projeto](https://youtu.be/IswwVdJREHI)

[Codebuild: Explicando a criação do projeto](https://youtu.be/iTkDmOhxIvo)

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](AQUI-DEVERA-TER-O-LINK-DO-VIDEO-QUE-SERA-EDITADO) Você verá como foi o passo que seguimos para realizar essa tarefa
