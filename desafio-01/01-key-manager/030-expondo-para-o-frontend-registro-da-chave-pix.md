# Expondo para o frontend: Registro da chave Pix

## Necessidades

Nosso frontend precisa registrar uma nova chave Pix para que o usuário possa gerar cobranças e efetuar pagamentos de cobranças diretamente do nosso aplicativo mobile. Portanto, a primeira funcionalidade que iremos expor via nossa API REST é justamente a operação para [registrar uma nova chave Pix](005-registrando-uma-nova-chave-pix.md).
   
## Restrições

Para registrar uma chave Pix, precisamos que o usuário informe os dados necessários para tal. Você pode levantar essas informações com detalhes a partir da [atividade de registro de chaves Pix que implementamos no módulo Key-Manager gRPC](005-registrando-uma-nova-chave-pix.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser registrada e armazenada no sistema;

- Em caso de chave já existente, deve-se retornar o status de erro `422-UNPROCESSABLE_ENTITY` com uma mensagem amigável para o usuário;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte
- Quer saber como criar um endpoint para atender requisições POST no Micronaut? [Este vídeo](https://www.youtube.com/watch?v=PWBEwECz4y4&feature=youtu.be) mostra como criar um controller que aceita esse tipo de requisição
- Quer ver como podemos validar os dados da requisição? [Neste vídeo](https://www.youtube.com/watch?v=Vw1uB_8EeX4&feature=youtu.be) é mostrado como você pode utilizar a Bean Validation para isso.
- Talvez você precise converter o objeto de entrada em um objeto de domínio. [Nesse vídeo](https://www.youtube.com/watch?v=Hoi3-Plm0uo&feature=youtu.be) mostramos uma forma de realizar essa conversão
- Quer saber como retornar um status code no Micronaut e adicionar informações nos Headers da Resposta? [Esse vídeo](https://www.youtube.com/watch?v=wgvIFkR5ea0&feature=youtu.be) tem uma explicação sobre como você pode fazer isso
- Não lembra o que é o protobuf? [Neste vídeo](https://www.youtube.com/watch?v=Rd7sLrPKDGM&feature=youtu.be) você vai ver uma introdução ao protobuf e ver o porquê utilizamos ele aqui
- Quer saber como lidar com erros do gRPC? [Neste vídeo](https://www.youtube.com/watch?v=dQYWWnnsHAc&feature=youtu.be) é mostrado como lidar com os possíveis erros de uma chamada remota

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=QBi4i7tpj98&feature=youtu.be) Você vai ver como foi o passo que seguimos para realizar essa tarefa
