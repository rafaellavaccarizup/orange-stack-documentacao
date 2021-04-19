# Testando a Remoção de chave Pix existente

## Necessidades

Nós finalizamos a implementação do endpoint responsável por [remover uma chave Pix existente](010-removendo-uma-chave-pix-existente.md), mas precisamos cobrí-la com testes automatizados antes de colocá-la em produção. 

A idéia de escrever testes é **encontrar bugs** antes de ir para produção. Quanto mais cedo encontrarmos um bug mais barato é sua resolução. Por esse motivo, precisamos encontrar bugs antes de deployar a aplicação em ambiente de produção (ou mesmo homologação).

Então, vamos cobrir com testes esse endpoint?
   
## Restrições

Escrever testes automatizados para o endpoint gRPC de Remoção de chave Pix implementado de tal forma que os testes garantam o que foi especificado na atividade.

Para guia-lo(a) nessa atividade, elencamos algumas restrições e pontos de atenção:

- favoreça a escrita de **testes de unidade** para lógicas de negócio que não fazem integração com serviços externos (banco de dados, APIs REST, mensageria, sistema de arquivos etc);
- favoreça a escrita de **testes de integração** para lógicas de negócio que conversam com serviços externos, como banco de dados, APIs REST etc;
- para tornar o teste mais próximo da produção, nos testes de integração **levante um servidor gRPC embarcado** e consuma os endpoints nos testes de integração;
- lembre-se de **testar os fluxos alternativos**, como cenários de erros do sistema ou entrada de dados inválida pelo usuário/serviço;
- favoreça o uso de um **banco de dados em memória** para facilitar a limpeza dos dados e simplificar o ambiente na sua pipeline de CI/CD;
- favoreça **mocks para chamadas à serviços externos**, como a API REST do Sistema ERP-ITAU e do Sistema Pix do BCB;
- fique sempre de olho na **cobertura do seu código**, especialmente nas branches de código, como `if`, `else`, `while`, `for`, `try-catch` etc;

Quer entender por que adotamos as restrições acima? [Assiste a esse vídeo](https://www.youtube.com/watch?v=IMvjNpG6320) para entender os detalhes do porquê acreditamos que esse é um bom caminho.

## Resultado Esperado

O que esperamos ao final dessa atividade e que também consideramos importante:

- ter um percentual de cobertura de no mínimo **90% do código de produção**;
- ter coberto cenários felizes (happy-path) e fluxos alternativos;
- não precisar de instruções especiais para preparar o ambiente ou para rodar sua bateria de testes;
- sua bateria de testes deve rodar tanto na sua IDE quanto via **linha de comando**;
- que outro desenvolvedor(a) do time consiga rodar facilmente a bateria de testes do seu serviço;

## Informações de suporte

- Ainda com dificuldade para escrever testes em Kotlin? Nesse artigo você relembra [como escrever testes com Kotlin e jUnit 5](](https://www.baeldung.com/kotlin/junit-5-kotlin));
- E os testes de integração com `@MicronautTest`, ainda está complicado entender a dinâmica? A [documentação do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#junit5) é sempre o melhor ponto de partida;
- Consumir um endpoint gRPC não é uma tarefa difícil, mas se não estiver simples então dá uma olhada na documentação do Micronaut sobre [como testar uma API gRPC](https://micronaut-projects.github.io/micronaut-grpc/snapshot/guide/index.html#_testing_the_server);
- Testes de integração que tocam o banco de dados e transações tem tudo a ver. Por isso, sempre que necessário releia [a documentação do Micronaut sobtre controle transacional nos testes](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_transaction_semantics);

## Como nós implementamos

- Está curioso(a) para saber como nós da Zup Edu escrevemos testes para esse endpoint gRPC? Não seja por isso, [nós gravamos esse vídeo](https://www.youtube.com/watch?v=Qqim-yNRkCU) para você perceber que não tem muito mistério nessa tarefa;

