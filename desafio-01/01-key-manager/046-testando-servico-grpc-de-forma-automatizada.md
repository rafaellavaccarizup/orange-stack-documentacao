# Testando o serviço gRPC de forma automatizada

## Necessidades

Nós finalizamos a implementação do serviço KeyManager-gRPC, e a partir de agora estamos nos preparando para coloca-lo em produção, mas antes precisamos testar nosso código para garantir que tudo esteja em perfeito funcionamento antes do deploy. Eu sei, eu sei... você já testou sua aplicação de ponta a ponta, não é mesmo? Embora tenhamos feito os testes com a ferramenta [BloomRPC](https://appimage.github.io/BloomRPC/) e exercitado a integração através do serviço KeyMangaer-REST nós fizemos isso de forma **manual**. Mas será que foi suficiente?

Testes manuais são ótimos e super válidos no ciclo de desenvolvimento de um sofware, mas não dá para ignorar que eles são caros. O que estou querendo dizer é que qualquer alteração no código requer que façamos todos os testes novamente, assim é possível descobrir o impacto da mudança. Enfim, muito trabalho para um(a) desenvolvedor(a), não é mesmo?

Some a isso o fato de que testes manuais são repetitivos e feitos por um ser humano, o que maximiza a chances de erros. Por esse motivo, vamos cobrir nosso código com **testes automatizados**, que nada mais são do que um programa que testa nosso programa, desse modo sempre que fizermos alguma mudança no código basta rodarmos nossa bateria de testes.

Ter uma bateria de testes bem escrita e funcionando nos permite ter um ciclo de entrega mais curto e seguro, nos ajuda a encontrar e corrigir erros mais rapidamente; e claro, o desenvolvedor(a) terá mais confiança em modificar ou refatorar código, afinal se ele cometer algum erro, por menor que seja, a bateria de testes vai alerta-lo(a) em questão de segundos.
   
## Restrições

Escrever testes automatizados para os endpoints gRPC de tal forma que os testes garantam que cada operação funcione como esperado.

Para guia-lo nessa atividade, elencamos algumas restrições e pontos de atenção:
- favoreça a escrita de **testes de unidade** para lógicas de negócio que não fazem integração com serviços externos (banco de dados, APIs REST, mensageria, sistema de arquivos etc);
- favoreça a escrita de **testes de integração** para lógicas de negócio que conversam com serviços externos, como banco de dados, APIs REST etc;
- para tornar o teste mais próximo da produção, nos testes de integração **levante um servidor gRPC** e consuma os endpoints nos testes de integração;
- lembre-se de **testar os fluxos alternativos**, como cenários erros do sistema ou entrada de dados inválida pelo usuário/serviço;
- favoreça o uso de um **banco de dados em memória** para facilitar a limpeza dos dados e simplificar o ambiente na sua pipeline de CI/CD;
- **mockar as chamadas à serviços externos**, como a API REST do Sistema ERP-ITAU e do Sistema Pix do BCB;
- fique sempre de olho na **cobertura do seu código**, especialmente nas branches de código, como `if`, `else`, `while`, `for`, `try-catch` etc;
- 

## Resultado Esperado

O que esperamos ao final dessa atividade e consideramos importante:
- ter um percentual de no mínimo **70% de cobertura de código**;
- ter coberto cenários felizes (happy-path) e fluxos alternativos;
- não precisar de instruções especiais para preparar o ambiente ou para rodar sua bateria de testes;
- sua bateria de testes deve rodar tanto na sua IDE quanto via **linha de comando**;

## Informações de suporte
- Não sabe como escrever um teste de unidade em Kotlin? Nesse artigo você aprende [como escrever testes com Kotlin e jUnit 5](](https://www.baeldung.com/kotlin/junit-5-kotlin));
- Está tendo dificuldades para escrever seu primeiro teste de integração com `@MicronautTest`? Não seja por isso, a [documentação do Micronaut](https://micronaut-projects.github.io/micronaut-test/latest/guide/#junit5) é nossa melhor amiga nesse momento;
- Dificuldade para configurar um banco de dados em memória? Nesse artigo você aprende [como configurar o banco H2 na sua aplicação](https://micronaut-projects.github.io/micronaut-sql/latest/guide/#jdbc);
- Não conseguiu mockar os serviços externos nos seus testes? Relaxa, na documentação do Micronaut você aprende [como usar a anotação `@MockBean`](https://micronaut-projects.github.io/micronaut-test/latest/guide/#_using_mockito_mocks);

## Como nós implementamos
Quer saber como nós da Zup Edu cobrimos com testes nosso serviço gRPC? [??? Neste vídeo ???](xxx) você vai ver como ficou a escrita dos testes de unidade e integração que implementamos;
