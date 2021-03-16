# Deployment do serviços: Uma abordagem ops


## Necessidades


Precisamos criar os arquivos necessários para deploy em um cluster kubernetes, seja via helm ou manifestos. 
Para uma melhor organização, crie a estrutura na raiz de seu projeto /pipeline/helm ou /pipeline/manifestos.

Como pré-requisito neste passo, precisamos que você adicione em seu artefato yaml (manifesto ou helm chart) 1 configmap
e 1 secrets e configurar sua aplicação para conectar em um banco de dados postgresql. Objetivando a segurança dos dados
(somos guardiões), nós iremos criar e configurar a string de conexão, usuário e senha nesses recursos. Segue um exemplo
de nomenclatura:

configmap: "NOME-DO-SEU-REPOSITORIO-configmap"

secrets: "NOME-DO-SEUREPOSITORIO-secrets"

Abaixo um exemplo, considerando o arquivo deployment.yaml de um helm chart:

```yml
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

Ainda sobre configmap e secrets, os seguintes valores de configmap estão configurados para o projeto keymanager grpc:

```
DB_URI: *string de conexão para o banco de dados*
DB_USER: *usuario do banco de dados*
DB_DIALECT: *dialeto do banco "POSTGRES"*
ITAU_URL: *url do serviço itau*
BCB_URL: *url do serviço bcb*
```

E esse valor na secrets:

```
DB_PASSWORD: *senha para acesso ao banco de dados*
```

Portanto, é uma boa prática, configurar sua app para receber esses valores como variáveis de ambiente.


Também precisamos que altere o service de sua app para LoadBalancer e adicione essa annotation:

```
  annotations:
    service.beta.kubernetes.io/aws-load-balancer-internal: "true"
```

O nome da imagem que deverá ser informada para deployment, deverá seguir o padrão: public.ecr.aws/d8b2x5c9/nome-do-seu-repositorio, ex:

```
public.ecr.aws/d8b2x5c9/orange-stack-pix-keymanager-grpc
```

## Informações de suporte

- Manifestos, yamls e kubernetes não soa familar? [Esse link](https://github.com/zup-academy/nosso-cartao-documentacao/blob/master/fatura/65.rodando-nossa-aplicacao-k8s.md) poderá ser útil.

- Nos links você encontrará maiores informações sobre helm

[helm 01](https://www.youtube.com/watch?v=6uoUNcM_JoY)
[helm 02](https://www.youtube.com/watch?v=9raXC_eTec8)
[helm 03](https://www.youtube.com/watch?v=UfCPMRV9J-c)

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](AQUI-DEVERA-TER-O-LINK-DO-VIDEO-QUE-SERA-EDITADO) Você verá como foi o passo que seguimos para realizar essa tarefa
