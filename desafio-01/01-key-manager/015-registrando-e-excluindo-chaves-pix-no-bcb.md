# Registrando e excluindo chaves Pix no Banco Central (BCB)

## Necessidades

Não basta registrar as chaves Pix no nosso sistema, elas precisam ser **registradas no Banco Central (BCB)**, caso contrário elas não poderão ser compartilhadas por nossos usuários nem utilizadas abertamente por diversas pessoas e instituições financeiras, como bancos, fintechs e meios de pagamento.

Por esse motivo, sempre que registrarmos uma chave Pix no nosso sistema ela também deve ser registrada globalmente, ou seja, no **Sistema Pix do BCB**. Não só isso, caso uma chave seja excluída do nosso sistema ela também deverá ser excluída no BCB.
   
## Restrições

Para registrar ou excluir uma chave Pix globalmente, precisamos nos integrar ao Sistema Pix do BCB por meio de uma API REST disponibilizada por eles. Para acessar a API e analisá-la, basta acessar o link abaixo:

[http://localhost:8082/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/](http://localhost:8082/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/)

Lembre-se, nosso sistema precisa manter um "link" entre a chave cadastrada no nosso sistema e a chave registrada no Sistema Pix do BCB, caso contrário não poderemos compartilhá-la nem excluí-la futuramente. Ou seja, uma chave desconhecida pelo BCB é uma chave inválida para qualquer fim.

O BCB será o sistema responsável por gerar a chave do tipo `ALEATORIA` em vez do nosso sistema. Portanto, nesse caso, o BCB irá ignorar qualquer chave enviada pelo nosso sistema.

Um detalhe importante, toda chave Pix registrada no BCB pelo nosso serviço deve usar o ISPB (Identificador de Sistema de Pagamento Brasileiro) do ITAÚ UNIBANCO S.A cujo valor é `60701190`.

## Resultado Esperado

- Ao cadastrar uma chave no nosso sistema, deve-se garantir que ela esteja devidamente registrada no Sistema Pix do BCB;

- Ao excluir uma chave existente no nosso sistema, deve-se garantir que ela tenha sido excluída primeiramente do Sistema Pix do BCB;

- Ao registrar uma chave do tipo `ALEATORIA` no BCB, deve-se também atualizar a chave no nosso sistema com a chave gerada pelo BCB;

- Uma chave Pix no nosso sistema somente poderá ser disponibilizada para uso dos nossos usuários (compartilhamento, geração de cobranças, pagamentos etc) quando ela estiver devidamente registrada e linkada à uma chave Pix existente no BCB;

## Informações de suporte

- Vai consumir a API REST do Sistema Pix do BCB? Aqui explicamos como podemos criar [um client HTTP com Micronaut](https://www.youtube.com/watch?v=9nPRHbToxAc&feature=youtu.be);

- Não sabe como consumir uma API REST que utiliza o formato XML? Não desanime, [nesse vídeo](https://www.youtube.com/watch?v=4MG_H-lKydI&feature=youtu.be) mostramos como é fácil fazer isso;

- Está com problemas para identificar por que seu client REST está retornando erro? Uma boa prática é [habilitar o log das chamadas HTTP](https://docs.micronaut.io/latest/guide/index.html#_debugging_tracing_the_http_client) do client REST do Micronaut;

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=qDEc_c5OYhY&feature=youtu.be) você vai ver como foi o passo que seguimos para realizar essa tarefa

