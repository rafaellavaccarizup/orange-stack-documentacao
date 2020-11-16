# Teste de performance

## Contexto

Toda nossa solução está pronta e geralmente antes de implantar o sistema em produção precisamos efetuar um teste de 
performance para garantir que o mesmo irá suportar a carga esperada!

## Necessidades

Realizar teste de carga utilizando o [Locust](https://locust.io/) e atingir a marca de 100 requisições por segunda (RPS) 
em apenas uma **única instância**

## Restrições

- O teste de carga deve utilizar o [Locust](https://locust.io/) que preparamos para você!

- O teste de carga deve utilizar as aplicações em [docker](https://docker.io/)

    - O docker deve ter um limite de 1 core de CPU
    
    - O docker deve ter um limite de 2GB de Memória

## Resultado Esperado

- A solução deve atingir 100 RPS com apenas uma **única instância** do serviço de **pagamento**

## Informações de suporte

## Sugestões de busca de conteúdo