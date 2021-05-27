# Testando a Exposição do serviço de registro de chave Pix

## Necessidades

Com o fim da implementação do endpoint responsável por [expor o registro de uma chave Pix](030-expondo-para-o-frontend-registro-da-chave-pix.md) o próximo passo é cobrir a funcionalidade com testes antes de mandá-la para produção.

Nessa tarefa não estamos mais expondo uma API gRPC, mas sim consumindo uma API criada por nós. Consegue perceber o impacto nos testes? Tudo que aprendemos até agora se aplica, mas em uma perspectiva diferente, pois agora somos um cliente gRPC.

Existem duas características importantes que ajudam a definir bons testes de unidade: **eles são isolados e independentes uns dos outros**. Isso quer dizer que um teste de unidade não quebra com mudanças no ambiente (data e hora, fuso horário, idioma, variáveis de ambiente etc) e que ele também pode ser executado em qualquer ordem (um teste não depende de outro). Se você conseguir aplicar essas mesmas características para os testes de integração então você tem o melhor dos dois mundos!

Você acha que consegue aplicar as características acima?
   
## Restrições

Escrever testes automatizados para a API REST que cuida da Exposição de Registro de chave Pix de tal forma que os testes garantam o que foi especificado na atividade.

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

- Não sabe como fazer testes de integração para APIs REST? Na [documentação do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#junit5) tem tudo que você precisa saber;
- Não lembra como usar Mockito com Kotlin? Então aproveita e lê [esse artigo excelente sobre Mockito](https://www.baeldung.com/kotlin/mockito);
- Não sabe como mockar uma API gRPC com Micronaut? Não esquenta, podemos sempre voltar para documentação do Micronaut sobre [como usar a anotação `@MockBean`](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);
- Criar factories com a anotação `@Factory` do Micronaut também é útil nos testes. Lembre-se de [utilizá-la onde necessária](https://docs.micronaut.io/latest/guide/index.html#factories);

## Como nós implementamos

- Quer saber como a gente da Zup Edu escreveu os testes para essa atividade? Dá uma olhada [no vídeo](https://www.youtube.com/watch?v=WVHbJEfmJxI) que gravamos;

