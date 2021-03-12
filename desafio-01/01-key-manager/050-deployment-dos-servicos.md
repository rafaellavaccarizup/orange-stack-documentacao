# Deployment do serviços: Uma abordagem ops

Neste desafio, o esperado é que o resultado de seus builds, sejam imagens docker e artefatos aptos a serem "deployados" em um cluster
kubernetes.

neste caso, usando Amazon EKS. O diagrama abaixo pode ajudar a ilustrar o cenário proposto:

![diagrama desafio deployment](../../recursos/diagramas/diagrama_desafio_deploy.png)

*Não se preocupe com a infraestrutura, todo o ambiente está pronto e aguardando o seu projeto =)*

## Necessidades

1. O artefato do build de seu projeto é uma imagem docker, por isso, é necessário criar o arquivo Dockerfile.

2. Precisamos criar os arquivos necessários para deploy em um cluster kubernetes, seja via helm ou manifestos. 
Para uma melhor organização, crie a estrutura na raiz de seu projeto /pipeline/helm ou /pipeline/manifestos.

Como pré-requisito neste passo, precisamos que você adicione em seu artefato yaml (manifesto ou helm chart) 1 configmap
e 1 secrets com os nomes:

configmap: "NOME-DO-SEU-REPOSITORIO-configmap"

secrets: "NOME-DO-SEUREPOSITORIO-secrets"

Abaixo um exemplo, considerando o arquivo deployment.yaml de um helm chart:

```
      containers:
        - name: {{ .Chart.Name }}
          securityContext:
            {{- toYaml .Values.securityContext | nindent 12 }}
          image: "{{ .Values.image.repository }}:{{ .Values.image.tag | default .Chart.AppVersion }}"
          imagePullPolicy: {{ .Values.image.pullPolicy }}
          ports:
            - name: http
              containerPort: 50051
              protocol: TCP
          livenessProbe:
            httpGet:
              path: /
              port: http
          readinessProbe:
            httpGet:
              path: /
              port: http
          envFrom:
            - configMapRef:
                name: meu-repositorio-configmap
            - secretRef:
                name: meu-repositorio-secrets
```

3. O codebuild precisa de um arquivo de configuração com instruções para construir o build. Nesse ponto o esperado é um arquivo
de build em /pipeline/buildspec.yaml

Segue um exemplo válido de buildspec.yaml para este cenário:

```
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
      - docker image ls
      - docker build -t $DEPLOYMENT_NAME . 
      - docker tag $DEPLOYMENT_NAME:$IMAGE_TAG $URL_REPO/$DEPLOYMENT_NAME:$IMAGE_TAG
      - docker image ls
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
OBS: Atente-se as linhas 77 e 98 pois tem algumas dicas que podem ser bem úteis.

4. Com o projeto pronto para ser constrúido na esteira de CI/CD, preencha [este](AQUI-DEVERÁ-TER-O-LINK-DO-FORMULARIO) formulário
com o seu repositório público.

Uma vez que o deployment seja bem sucedido, devolveremos o endpoint para que você possa validar.

OBS: Como exibido no diagrama, será necessário conectar na vpn corporativa para acesso ao link.

## Informações de suporte

- Dúvidas em como criar um Dockerfile [Esse link](LINK-PARA-O-CONTEUDO) tem uma explicação sobre como você pode fazer isso.
- Manifestos, yamls e kubernetes não soa familar? [Esse link](LINK-PARA-O-CONTEUDO) poderá ser útil.
- Neste [link](LINK-PARA-O-CONTEUDO) você encontrará maiores informações sobre helm
- Caso queira relembrar sobre o funcionamento do codebuild, esse [link](LINK-PARA-O-CONTEUDO) pode ajudar.

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](AQUI-DEVERA-TER-O-LINK-DO-VIDEO-QUE-SERA-EDITADO) Você verá como foi o passo que seguimos para realizar essa tarefa
