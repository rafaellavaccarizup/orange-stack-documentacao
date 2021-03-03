# Setup do Projeto - Key-Manager gRPC

## Objetivo

Sabemos que está ansioso(a) para começar a codificar, porém antes precisamos preparar nosso ambiente, portanto esse 
será nosso objetivo nessa tarefa.

## Descrição

Nessa tarefa precisamos criar um projeto para atender as funcionalidades do **Key-Manager**, para tal, temos alguns 
pré-requisitos de linguagem de programação e tecnologia, pois precisamos que esse projeto seja evoluído e mantido por 
anos, portanto é extremamente importante a escolha das mesmas.

Nosso mais experiente membro do time, sugeriu os seguintes itens:

- Vamos escrever todo código com a linguagem de programação [Kotlin](https://kotlinlang.org/);
- Também vamos usar as tecnologias [Micronaut](http://micronaut.io/) e [gRPC](https://grpc.io/) para criar nossa API;
- E por fim, usaremos o [Gradle](https://gradle.org/) para rodar nosso build, testes e gerenciar nossas dependências;

### Hora de começar, por onde começar?

Existem várias maneiras de se começar um projeto com Micronaut, uma forma simples e bastante utilizada no mercado é via [Micronaut Launch!](https://micronaut.io/launch/)

* Não lembra como criar um projeto gRPC com Micronaut? Não seja por isso, os [primeiros minutos desse vídeo](https://www.youtube.com/watch?v=_53_sQp2bR4&feature=youtu.be) podem te ajudar;
* Não esqueça de [configurar seu IntelliJ](https://www.youtube.com/watch?v=dBXbbrG_UWU&feature=youtu.be) para seu projeto Micronaut;

## Resultado Esperado

Projeto gerado com as tecnologias sugeridas:

- [Kotlin](https://kotlinlang.org/)
- [Micronaut](http://micronaut.io/) e [gRPC](https://grpc.io/)
- [Gradle](https://gradle.org/)

## Informações de suporte

- Está recebendo o erro `Caused by: java.lang.ClassNotFoundException: org.fusesource.jansi.WindowsAnsiOutputStream` ao startar sua aplicação no Windows? Não se assuste! Talvez o problema esteja relacionado [com essa issue](https://stackoverflow.com/questions/57855094/windowsansioutputstream-class-not-found) do Micronaut;
