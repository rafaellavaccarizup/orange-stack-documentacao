# Testando a Consulta de dados de uma chave Pix

## Necessidades

Com o fim da implementação do endpoint responsável por [consultar dados de uma chave Pix](020-consultando-os-dados-de-uma-chave-pix.md) o próximo passo é cobrir a funcionalidade com testes antes de mandá-la para produção.

**Quanto mais próximo um teste é do mundo real, mais difícil de escrevê-lo**. Não é à toa que testes de unidade são mais simples de escrever e manter, afinal, não há nenhuma comunicação com sistemas externos, o código de produção é exercitado de forma isolada. Em contrapartida, testes de integração requerem maior preparo, onde boa parte de sua dificuldade está na construção do cenário. Quando falo de cenário, eu falo de popular as tabelas no banco de dados, mockar chamadas à APIs, limpar estado em disco ou cache, ou mesmo levantar ambientes inteiros com serviços externos.

Esse exercício vai te desafiar um pouco! Bora lá escrever os testes?
   
## Restrições

Escrever testes automatizados para o endpoint gRPC de Consulta de dados de uma chave Pix implementado de tal forma que os testes garantam o que foi especificado na atividade.

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

- Você sabia que todo Repository no Micronaut possui o método `.deleteAll()`? Ele pode te ajudar na limpeza das tabelas do banco de dados;
- Cuidado com resultados falso-positivo ao preparar cenários de testes! A documentação do Micronaut te ajuda a [controlar as transações em cada método de teste](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_transaction_semantics);
- Não sabe como mockar código Kotlin com Mockito? Aqui [um artigo excelente sobre Mockito](https://www.baeldung.com/kotlin/mockito) para você entender a dinâmica dos mocks;
- Esqueceu como mockar os clients HTTP com Micronaut? Relaxa, na documentação do Micronaut você aprende [como usar a anotação `@MockBean`](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);

## Como nós implementamos

- Quer saber como a gente da Zup Edu escreveu os testes para essa atividade? Dá uma olhada [??? no vídeo ???](xxx) que gravamos;

