# Testando a Listagem de chaves Pix do cliente

## Necessidades

Mais uma tarefa finalizada, mas isso não quer dizer que acabou!

Nós finalizamos a implementação do endpoint responsável por [listar todas as chaves Pix do cliente](021-listando-todas-as-chaves-pix-do-cliente.md), mas agora precisamos cobri-la com testes automatizados antes de colocá-la em produção.

**Escrever testes automatizados é uma arte, quanto mais você pratica melhor você fica**. Por exemplo, chega uma hora que você bate o olho num trecho de código de produção e você consegue enxergar a maioria, senão todos, os cenários de testes necessários para cobrir aquele código.
   
## Restrições

Escrever testes automatizados para o endpoint gRPC de Listagem de chaves Pix do cliente implementado de modo que os testes garantem o que foi especificado na atividade.

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
- Sua bateria de testes deve rodar tanto na sua IDE quanto via **linha de comando**;
- Que outro desenvolvedor(a) do time consiga rodar facilmente a bateria de testes do seu serviço;

## Informações de suporte

- Você sabia que os métodos anotados com `@BeforeEach` e `@AfterEach` são transacionais por padrão no Micronaut? Eles são um excelente local para preparar cenários compartilhados entre os diversos métodos de testes;
- Preparar os diversos cenários de testes é o maior desafio para testes de integração. Portanto, não esqueça de ficar ligado(a) em [como gerenciar as transações com Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_transaction_semantics);

## Como nós implementamos

- Testar essa atividade não foi difícil, mas ainda assim você quer ver como nós da Zup Edu fizemos? Cola junto na gente e assiste [esse vídeo](https://www.youtube.com/watch?v=ehMgmMtyPKQ) que gravamos para você;

