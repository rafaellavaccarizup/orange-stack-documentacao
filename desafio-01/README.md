# Desafio: Pix

Recentemente o Banco Central do Brasil (BCB) trouxe ao mercado o **Pix**. Em poucas palavras, o Pix é um novo meio de pagamentos para fazer transferências de forma rápida, sem esperar dias para que o pagamento “caia” na conta de quem o receberá ou ter que fazê-los só em dias da semana, no horário comercial. Além de poder transferir dinheiro para outras pessoas, será possível também fazer pagamentos a estabelecimentos usando o Pix, por exemplo.

Com o Pix, pagamentos e transferências são **concluídos em alguns segundos** e podem ser feitos a qualquer horário e dia, incluindo finais de semana e feriados. O Pix vai, portanto, facilitar e agilizar as transferências de valores entre pessoas e estabelecimentos comerciais, o pagamento de contas e até recolhimento de impostos e taxas de serviços, entre outras possibilidades.

Vale dizer que para enviar ou receber um Pix, não é necessário fazer nenhum cadastro ou baixar um aplicativo – ele pode ser usado diretamente no aplicativo de sua instituição; é necessário somente que ela ofereça esse meio de pagamento. 

Dessa forma, nosso **objetivo** é garantir que nossos usuários possam:
1. efetuar pagamentos e transferências via Pix na nossa plataforma;
2. registrar suas chaves Pix em nossa plataforma usando suas informações pessoais: CPF, telefone celular, email ou uma chave aleatória. Com uma chave registrada, será possível receber e pagar via Pix;

Para facilitar ainda mais o entendimento sobre o Desafio PIX e arquitetura proposta para esse projeto, nós [gravamos esse vídeo](https://www.youtube.com/watch?v=pe0m6ATJlOI&feature=youtu.be) para que você não tenha dúvidas!

# Entendendo a Arquitetura do Projeto

Por o Pix se tratar de produto novo no mercado, decidimos criar uma **fachada (façade)** com o intuito aproveitar e estender os recursos existentes na nossa atual plataforma (ERP-Itau) e assim diminuir o impacto das mudanças na mesma. Portanto, para esse projeto, nossa arquitetura será baseada em microservices para trazer maior flexibilidade e produtividade durante o desenvolvimento. Não só isso, com essa distribuição dos módulos nós poderemos escalá-los de forma independente e isolada.

![Arquitetura do projeto Pix](../recursos/diagramas/PIX.png "Arquitetura do projeto Pix")

Para desenvolver todas as funcionalidades, precisaremos implementar 4 (quatro) microsserviços utilizando a **Orange Stack**, que nada mais é do que as tecnologias, serviços nas nuvens e práticas de deployment recomendadas pelas equipes de engenharia da Zup e Itau. Ao falarmos dessa stack, nós falamos de tecnologias como:

* Kotlin como linguagem de programação dos microsserviços;
* Micronaut e todos seus módulos como base de desenvolvimento para tirar proveitos de recursos nas nuvens;
* gRPC para integração dos microsserviços dentro da nossa infraestrutura;
* Kafka para mensageria assincrona e desacoplamento entre os microsserviços;
* Redis para cache distribuído;
* OAuth2, OpenId e Keycloak para segurança: autenticação e autorização;
* RDBMS (PostgreSQL e MySQL) e DynamoDB para armazenar e gerenciar nossos dados;
* e vários serviços especializados da AWS;

Falando em microsserviços, nossos 4 serviços serão estes:

- **KeyManager-gRPC**: microsserviço responsável por fazer todo o gerenciamento das chaves Pix dos nossos clientes (usuários), além de ser o ponto central de comunicação da nossa arquitetura para busca de chaves;
- **KeyManager-REST**: microsserviço responsável por expor serviço KeyManager-gRPC através de uma API REST de tal forma que ela possa ser consumida pelo time de frontend de forma eficiente e segura;
- **Payment-gRPC**: microsserviço responsável por gerar cobranças Pix que serão compartilhadas via QR Code por nossos usuários; junto isso, haverá também a possibilidade de efetuar pagamentos a partir de um QR Code;
- **Payment-REST**: assim como o KeyManager-REST, esse microsserviço servirá de fachada para o time de frontend, ou seja, ele cuidará de expor uma API REST para os endpoints do microsserviço Payment-gRPC;

Em cada microsserviço precisamos ficar a atentos a requisitos não-funcionais como performance, escalabilidade, segurança e resiliência, além da qualidade e design do código produzido.

# Indice

- [00 - Desafio: Pix](#desafio-pix)
- [01 - Arquitetura do projeto e tecnologias](#entendendo-a-arquitetura-do-projeto)
    - [01.1 - Setup do ambiente](005-setup-do-ambiente.md)
- [02 - Modulo Key-Manager](01-key-manager/)
    - [02.1 - Setup do projeto: key-manager-grpc](01-key-manager/001-setup-do-projeto-key-manager-grpc.md)
    - [02.2 - Registrando uma nova chave Pix](01-key-manager/005-registrando-uma-nova-chave-pix.md)
    - [02.3 - Testando o Registro de chave Pix](01-key-manager/006-testando-registro-de-chave-pix.md)
    - [02.4 - Removendo uma chave Pix existente](01-key-manager/010-removendo-uma-chave-pix-existente.md)
    - [02.5 - Testando a Remoção de chave Pix existente](01-key-manager/011-testando-remocao-de-chave-pix-existente.md)
    - [02.6 - Registrando e excluindo chaves Pix no Banco Central (BCB)](01-key-manager/015-registrando-e-excluindo-chaves-pix-no-bcb.md)
    - [02.7 - Testando o Registro e Exclusão de chaves Pix no BCB](01-key-manager/016-testando-registro-e-exclusao-de-chaves-pix-no-bcb.md)
    - [02.8 - Consultando os dados de uma chave Pix](01-key-manager/020-consultando-os-dados-de-uma-chave-pix.md)
    - [02.9 - Testando a Consulta de dados de uma chave Pix](01-key-manager/021-testando-consulta-de-dados-de-uma-chave-pix.md)
    - [02.10 - Listando todas as chaves Pix do cliente](01-key-manager/021-listando-todas-as-chaves-pix-do-cliente.md)
    - [02.11 - Testando a Listagem de chaves Pix do cliente](01-key-manager/023-testando-listagem-de-chaves-pix.md)
    - [02.12 - Setup do projeto: key-manager-rest](01-key-manager/025-setup-do-projeto-key-manager-rest.md)
    - [02.13 - Expondo para o frontend: Registro da chave Pix](01-key-manager/030-expondo-para-o-frontend-registro-da-chave-pix.md)
    - [02.14 - Testando a Exposição do serviço de registro de chave Pix](01-key-manager/031-testando-exposicao-de-registro-de-chave-pix.md)
    - [02.15 - Expondo para o frontend: Remoção de uma chave Pix existente](01-key-manager/035-expondo-para-o-frontend-remocao-de-uma-chave-pix-existente.md)
    - [02.16 - Testando a Exposição do serviço de remoção de uma chave Pix existente](01-key-manager/036-testando-exposicao-de-remocao-de-uma-chave-pix-existente.md)
    - [02.17 - Expondo para o frontend: Detalhamento de uma chave Pix](01-key-manager/040-expondo-para-o-frontend-detalhamento-de-uma-chave-pix.md)
    - [02.18 - Testando a Exposição do serviço de detalhamento de uma chave Pix existente](01-key-manager/041-testando-exposicao-de-detalhamento-de-uma-chave-pix-existente.md)
    - [02.19 - Expondo para o frontend: Listagem de todas as chaves Pix](01-key-manager/045-expondo-para-o-frontend-listagem-de-chaves-pix.md)
    - [02.20 - Testando a Exposição do serviço de listagem de chaves Pix](01-key-manager/046-testando-exposicao-de-listagem-de-chaves-pix.md)
    - [02.21 - Containerizando nossas aplicações em imagens Docker](01-key-manager/050-deployment-dos-servicos-dockerfile.md)
    - [02.22 - Preparando as aplicações para o Kubernetes](01-key-manager/055-deployment-dos-servicos-manifestos-k8s..md)
    - [02.23 - Configurando nossa pipeline com AWS CodeBuild](01-key-manager/060-deployment-dos-servicos-codebuild.md)
    - [02.24 - Deployando as aplicações e validando na AWS](01-key-manager/065-deployment-dos-servicos-validando.md)
- [~~03 - Modulo Payment (Cobrança)~~](02-payment)
    - [~~03.1 - Setup do projeto: payment-grpc~~](02-payment/001-setup-do-projeto-payment-grpc.md)
    - [~~03.2 - Gerando uma cobrança via Pix para QR Code~~](02-payment/005-gerando-uma-cobranca-via-pix-para-qrcode.md)
    - [~~03.3 - Pagando uma cobrança via Pix~~](02-payment/010-pagando-uma-cobranca-via-pix.md)
    - [~~03.4 - Setup do projeto: payment-rest~~](02-payment/015-setup-do-projeto-payment-rest.md)
    - [~~03.5 - Expondo para o frontend: Gerando cobranças via Pix para QR Code~~](02-payment/020-expondo-para-o-frontend-gerando-cobrancas-via-pix-para-qrcode.md)
    - [~~03.6 - Expondo para o frontend: Pagando cobranças via Pix~~](02-payment/025-expondo-para-o-frontend-pagando-cobrancas-via-pix.md)
- [~~04 - Segurança~~](03-seguranca)
    - [~~04.1 - Autenticação e Autorização~~](03-seguranca/001-autenticacao-e-autorizacao.md)
    - [~~04.2 - Validando a chave Pix do usuário logado~~](03-seguranca/005-validando-a-chave-pix-do-usuario-logado.md)
- [~~05 - Resiliência e Disponibilidade~~](04-resiliencia-e-disponibilidade)
    - [~~05.1 - O que acontece se o microservice Payment ficar fora do ar?~~](04-resiliencia-e-disponibilidade/001-o-que-acontece-se-o-microservice-payment-ficar-fora-do-ar.md)
    - [~~05.2 - O que acontece se o microservice Key-Manager ficar fora do ar?~~](04-resiliencia-e-disponibilidade/005-o-que-acontece-se-o-microservice-key-manager-ficar-fora-do-ar.md)
    - [~~05.3 - Melhorando a disponibilidade do microservice Payment através de Cache Distribuído~~](04-resiliencia-e-disponibilidade/010-melhorando-a-disponibilidade-do-microservice-payment-atraves-de-cache-distribuido.md)
    - [~~05.4 - Definindo timeout para todas as chamadas remotas~~](04-resiliencia-e-disponibilidade/015-definindo-timeout-para-todas-as-chamadas-remotas.md)
    - [~~05.5 - Lidando com falhas parciais e transientes: habilitando Retry~~](04-resiliencia-e-disponibilidade/020-lidando-com-falhas-parciais-e-transientes-habilitando-retry.md)

# Outras informações 

Aqui estão listados alguns artigos, documentações e links interessantes caso você queira se contextualizar um pouco mais sobre o Pix e seu uso no mundo real:

- [Bacen OpenAPI 3.0: Especificação da API Pix](https://github.com/bacen/pix-api)
- [Bacen OpenAPI: Especificação da API DICT - Diretório de Identificadores de Contas Transacionais do PIX](https://github.com/bacen/pix-dict-api)