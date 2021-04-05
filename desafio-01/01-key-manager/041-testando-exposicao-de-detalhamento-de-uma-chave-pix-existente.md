# Testando o Exposição do serviço de detalhamento de uma chave Pix existente

## Necessidades

É hora de cobrir o código de produção do endpoint que [expõe o detalhamento de uma chave Pix existente](040-expondo-para-o-frontend-detalhamento-de-uma-chave-pix.md) com testes automatizados.

Lembre-se, tudo que estudamos e aprendemos até este momento também se aplica para testes de APIs REST e também para código que consome alguma API gRPC.
   
## Restrições

Escrever testes automatizados para a API REST que cuida da Exposição do Detalhamento de uma chave Pix existente de modo que os testes garantam o que foi especificado na atividade.

Para guia-lo(a) nessa atividade, elencamos algumas restrições e pontos de atenção:

- favoreça a escrita de **testes de unidade** para lógicas de negócio que não fazem integração com serviços externos (banco de dados, APIs REST, mensageria, sistema de arquivos etc);
- favoreça a escrita de **testes de integração** para lógicas de negócio que conversam com serviços externos, como banco de dados, APIs REST etc;
- para tornar o teste mais próximo da produção, nos testes de integração **levante um servidor gRPC embarcado** e consuma os endpoints nos testes de integração;
- lembre-se de **testar os fluxos alternativos**, como cenários de erros do sistema ou entrada de dados inválida pelo usuário/serviço;
- favoreça o uso de um **banco de dados em memória** para facilitar a limpeza dos dados e simplificar o ambiente na sua pipeline de CI/CD;
- favoreça **mocks para chamadas à serviços externos**, como a API REST do Sistema ERP-ITAU e do Sistema Pix do BCB;
- fique sempre de olho na **cobertura do seu código**, especialmente nas branches de código, como `if`, `else`, `while`, `for`, `try-catch` etc;

## Resultado Esperado

O que esperamos ao final dessa atividade e que também consideramos importante:

- ter um percentual de cobertura de no mínimo **90% do código de produção**;
- ter coberto cenários felizes (happy-path) e fluxos alternativos;
- não precisar de instruções especiais para preparar o ambiente ou para rodar sua bateria de testes;
- sua bateria de testes deve rodar tanto na sua IDE quanto via **linha de comando**;
- que outro desenvolvedor(a) do time consiga rodar facilmente a bateria de testes do seu serviço;

## Informações de suporte

- Ainda com dúvidas sobre testes de APIs REST? A [documentação do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#junit5) é sempre o melhor ponto de partida;
- Apanhando pro Mockito? Talvez seja melhor reler [esse artigo sobre essa biblioteca incrível](https://www.baeldung.com/kotlin/mockito);
- Esqueceu como mockar os clients gRPC com Micronaut? A documentação do Micronaut está aí para isso, basta ler sobre [como usar a anotação `@MockBean`](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);
- Criar factories com a anotação `@Factory` do Micronaut também é útil nos testes. Lembre-se de [utilizá-la onde necessária](https://docs.micronaut.io/latest/guide/index.html#factories);

## Como nós implementamos

- Quer saber como a gente da Zup Edu escreveu os testes para essa atividade? Dá uma olhada [??? no vídeo ???](xxx) que gravamos;

