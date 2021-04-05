# Testando o Registro e Exclusão de chaves Pix no BCB

## Necessidades

Mais uma tarefa finalizada, mas isso não quer dizer que acabou!

Precisamos ajustar nossos testes automatizados com as mudanças feitas no código de produção dos endpoints responsáveis por [registrar uma nova chave Pix](005-registrando-uma-nova-chave-pix.md) e  [remover uma chave Pix existente](010-removendo-uma-chave-pix-existente.md), afinal eles agora se [integram com a API REST do Sistema Pix do BCB](015-registrando-e-excluindo-chaves-pix-no-bcb.md). 

Um aspecto importante dos testes é que eles **evoluem juntamente com o código de produção**. Assim como nosso código de produção, o código de testes também precisa ser mantido, refatorado e melhorado durante o ciclo de vida do software. Ignorar isso é ter uma bateria de testes frágil, lenta e que pode gerar resultados falso-positivo para as lógicas de negócio que escrevemos.

Só eu acho que temos que evoluir o código de testes? :-)
   
## Restrições

Evoluir e adaptar o código de testes para os endpoints gRPC de Registro e Remoção de chave Pix de modo que os testes garantam a corretude do foi [especificado na atividade de integração com o BCB](/mnt/c/Users/Zupper/Development/Zup_Academy/Orange-Stack/documentacao-orange-stack/desafio-01/01-key-manager/015-registrando-e-excluindo-chaves-pix-no-bcb.md).

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

- Não sabe como mockar código Kotlin com Mockito? Aqui [um artigo excelente sobre Mockito](https://www.baeldung.com/kotlin/mockito) para você entender a dinâmica dos mocks;
- Não sabe como mockar os clients HTTP com Mockito e Micronaut? Relaxa, na documentação do Micronaut você aprende [como usar a anotação `@MockBean`](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);
- Não lembra como o Micronaut gerencia as transações com o banco de dados durante os testes? Mais uma vez [a documentação](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_transaction_semantics) está aí para anos ajudar;
- Quer se aprofundar na biblioteca do Mockito? Essa [série de artigos sobre Mockito](https://www.baeldung.com/mockito-series) vai te ajudar a dominá-lo de ponta a ponta;

## Como nós implementamos

- Curioso para saber como ajustamos nossos testes para as mudanças do código de produção? Fica tranquilo, a gente gravou [??? esse vídeo ???](xxx) para te ajudar a entender o que fizemos;

