# Expondo para o frontend: Listagem de todas as chaves Pix

## Necessidades

Nosso usuário precisa visualizar todas suas chaves Pix cadastradas até o momento, para isso precisamos expor em nossa API REST a [operação de listagem de chaves Pix](021-listando-todas-as-chaves-pix-do-cliente.md).
   
## Restrições

Listar todas as chaves Pix do usuário a partir das informações da [atividade de listagem de chaves Pix que implementamos no módulo Key-Manager gRPC](021-listando-todas-as-chaves-pix-do-cliente.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

## Resultado Esperado

- Em caso de sucesso, deve-se retornar uma coleção com todas as chaves Pix;
  
- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte
- Quer saber como retornar um objeto em formato JSON com o Micronaut? [Esse vídeo](https://www.youtube.com/watch?v=PML9YWZUnbk&feature=youtu.be) tem uma explicação sobre como você pode fazer isso

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=Eki5B21v6zw&feature=youtu.be) Você vai ver como foi o passo que seguimos para realizar essa tarefa
