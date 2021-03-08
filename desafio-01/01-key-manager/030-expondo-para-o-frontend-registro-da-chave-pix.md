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

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=QBi4i7tpj98&feature=youtu.be) Você vai ver como foi o passo que seguimos para realizar essa tarefa
