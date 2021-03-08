# Desafio: Pix

Recentemente o Banco Central do Brasil (BCB) trouxe ao mercado o **Pix**. Em poucas palavras, o Pix é um novo meio de pagamentos para fazer transferências de forma rápida, sem esperar dias para que o pagamento “caia” na conta de quem o receberá ou ter que fazê-los só em dias da semana, no horário comercial. Além de poder transferir dinheiro para outras pessoas, será possível também fazer pagamentos a estabelecimentos usando o Pix, por exemplo.

Com o Pix, pagamentos e transferências são **concluídos em alguns segundos** e podem ser feitos a qualquer horário e dia, incluindo finais de semana e feriados. O Pix vai, portanto, facilitar e agilizar as transferências de valores entre pessoas e estabelecimentos comerciais, o pagamento de contas e até recolhimento de impostos e taxas de serviços, entre outras possibilidades.

Vale dizer que para enviar ou receber um Pix, não é necessário fazer nenhum cadastro ou baixar um aplicativo – ele pode ser usado diretamente no aplicativo de sua instituição; é necessário somente que ela ofereça esse meio de pagamento. 

Dessa forma, nosso **objetivo** é garantir que nossos usuários possam:
1. efetuar pagamentos e transferências via Pix na nossa plataforma;
2. registrar suas chaves Pix em nossa plataforma usando suas informações pessoais: CPF, telefone celular, email ou uma chave aleatória. Com uma chave registrada, será possível receber e pagar via Pix;

# Entendendo a Arquitetura do Projeto

Por o Pix se tratar de produto novo no mercado, decidimos criar uma **fachada (façade)** com o intuito aproveitar e estender os recursos existentes na nossa atual plataforma e assim diminuir o impacto das mudanças na mesma. Portanto, para esse projeto, nossa arquitetura será baseada em microservices para trazer maior flexibilidade e produtividade durante o desenvolvimento. Não só isso, com essa distribuição dos módulos nós poderemos escalá-los de forma independente e isolada.

![Arquitetura do projeto Pix](../../recursos/diagramas/PIX.png "Arquitetura do projeto Pix")

# Indice

- [00 - Desafio: Pix](README.md)
- [01 - Arquitetura do projeto e tecnologias](../001-arquitetura-do-projeto-e-ambiente.md)
    - [01.1 - Setup do ambiente](../005-setup-do-ambiente.md)
- [02 - Modulo Key-Manager](/)
    - [02.1 - Setup do projeto: key-manager-grpc](001-setup-do-projeto-key-manager-grpc.md)
    - [02.2 - Registrando uma nova chave Pix](005-registrando-uma-nova-chave-pix.md)
    - [02.3 - Removendo uma chave Pix existente](010-removendo-uma-chave-pix-existente.md)
    - [02.4 - Registrando e excluindo chaves Pix no Banco Central (BCB)](015-registrando-e-excluindo-chaves-pix-no-bcb.md)
    - [02.5 - Consultando os dados de uma chave Pix](020-consultando-os-dados-de-uma-chave-pix.md)
    - [02.6 - Listando todas as chaves Pix do cliente](021-listando-todas-as-chaves-pix-do-cliente.md)
    - [02.7 - Setup do projeto: key-manager-rest](025-setup-do-projeto-key-manager-rest.md)
    - [02.8 - Expondo para o frontend: Registro da chave Pix](030-expondo-para-o-frontend-registro-da-chave-pix.md)
    - [02.9 - Expondo para o frontend: Remoção de uma chave Pix existente](035-expondo-para-o-frontend-remocao-de-uma-chave-pix-existente.md)
    - [02.10 - Expondo para o frontend: Detalhamento de uma chave Pix](040-expondo-para-o-frontend-detalhamento-de-uma-chave-pix.md)
    - [02.11 - Expondo para o frontend: Listagem de todas as chaves Pix](045-expondo-para-o-frontend-listagem-de-chaves-pix.md)

# Outras informações 

Aqui estão listados alguns artigos, documentações e links interessantes caso você queira se contextualizar um pouco mais sobre o Pix e seu uso no mundo real:

- [Bacen OpenAPI 3.0: Especificação da API Pix](https://github.com/bacen/pix-api)
- [Bacen OpenAPI: Especificação da API DICT - Diretório de Identificadores de Contas Transacionais do PIX](https://github.com/bacen/pix-dict-api)