# Testando a Exposição do serviço de remoção de uma chave Pix existente

## Necessidades

Agora vamos escrever os testes para o código de produção do endpoint responsável por [expor a exclusão de uma chave Pix existente](035-expondo-para-o-frontend-remocao-de-uma-chave-pix-existente.md).

Quanto **menor a dependência com meio externo melhor para manutenção dos testes**. Depender do estado de bancos de dados, cache e outros sistemas terceiros pode simplificar a escrita do código de testes, da preparação do ambiente e principalmente diminuir a fragilidade dos testes.

Lembre-se, tudo que estudamos e aprendemos até este momento também se aplica para testes de APIs REST e também para código que consome alguma API gRPC.
   
## Restrições

Escrever testes automatizados para a API REST que cuida da Exposição de Remoção de uma chave Pix existente de modo que os testes garantem o que foi especificado na atividade.

Para guiá-lo(a) nessa atividade, elencamos algumas restrições e pontos de atenção:

- Favoreça a escrita de **testes de unidade** para lógicas de negócio que não fazem integração com serviços externos (banco de dados, APIs REST, mensageria, sistema de arquivos etc);
- Favoreça a escrita de **testes de integração** para lógicas de negócio que conversam com serviços externos, como banco de dados, APIs REST etc;
- Para tornar o teste mais próximo da produção, nos testes de integração **levante um servidor gRPC embarcado** e consuma os endpoints nos testes de integração;
- Lembre-se de **testar os fluxos alternativos**, como cenários de erros do sistema ou entrada de dados inválida pelo usuário/serviço;
- Favoreça o uso de um **banco de dados em memória** para facilitar a limpeza dos dados e simplificar o ambiente na sua pipeline de CI/CD;
- Favoreça **mocks para chamadas à serviços externos**, como a API REST do Sistema ERP-ITAÚ e do Sistema Pix do BCB;
- Fique sempre de olho na **cobertura do seu código**, especialmente nas branches de código, como `if`, `else`, `while`, `for`, `try-catch` etc;

Quer entender por que adotamos as restrições acima? [Assiste a esse vídeo](https://www.youtube.com/watch?v=IMvjNpG6320) para entender os detalhes do porquê acreditamos que esse é um bom caminho.

## Resultado Esperado

O que esperamos ao final dessa atividade e que também consideramos importante:

- Ter um percentual de cobertura de no mínimo **90% do código de produção**;
- Ter coberto cenários felizes (happy-path) e fluxos alternativos;
- Não precisar de instruções especiais para preparar o ambiente ou para rodar sua bateria de testes;
- sua bateria de testes deve rodar tanto na sua IDE quanto via **linha de comando**;
- que outro desenvolvedor(a) do time consiga rodar facilmente a bateria de testes do seu serviço;

## Informações de suporte

- Não sabe como fazer testes de integração para APIs REST? Na [documentação do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#junit5) tem tudo que você precisa saber;
- Não lembra como usar Mockito com Kotlin? Então aproveita e lê [esse artigo excelente sobre Mockito](https://www.baeldung.com/kotlin/mockito);
- Ainda com dificuldade de mockar um client gRPC? A documentação do Micronaut fala o suficiente sobre [como mockar beans no contexto do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);
- Criar factories com a anotação `@Factory` do Micronaut também é útil nos testes. Lembre-se de [utilizá-la onde necessária](https://docs.micronaut.io/latest/guide/index.html#factories);

## Como nós implementamos

- Quer saber como a gente da Zup Edu escreveu os testes de unidade e integração para essa atividade? Dá uma olhada [no vídeo](https://www.youtube.com/watch?v=2niu752XIWk) que gravamos;

