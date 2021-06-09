# Removendo uma chave Pix existente

## Necessidades

Nosso usuário precisa excluir suas chaves Pix cadastradas, pois dessa forma, se necessário, ele poderá recriar uma chave associada à uma nova conta corrente ou poupança.
   
## Restrições

Para excluir uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Pix ID** (identificador interno da chave Pix) deve ser obrigatório;

- **Identificador do cliente** deve ser obrigatório:
   - Código interno do cliente na Instituição Financeira existente no [Sistema ERP do Itaú](http://localhost:9091/api/v1/private/contas/todas);
   
A chave pode ser removida somente pelo seu dono (cliente).

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser excluída do sistema;

- Em caso de chave não encontrada, deve-se retornar status de erro `NOT_FOUND` com uma mensagem amigável para o usuário final;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

- Os dados do cliente e de sua conta corrente **devem ser obtidos do [Sistema ERP do Itaú](http://localhost:9091/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/)**;
  
- Não lembra como tratar erro e retornar um status `NOT_FOUND`? Nesse [vídeo conversamos sobre tratamento de erros com gRPC](https://www.youtube.com/watch?v=bIuEINzEmKs&feature=youtu.be);
  
- Precisa validar os dados de entrada de forma declarativa? Aqui discutimos como usar as [anotações da Bean Validation](https://www.youtube.com/watch?v=Vw1uB_8EeX4&feature=youtu.be);

## Sugestões de busca de conteúdo

- Quer entender um pouco mais sobre os possíveis status numa API gRPC? [Aqui você pode conhecer cada um deles e entender quando utilizá-los](https://developers.google.com/maps-booking/reference/grpc-api/status_codes)

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=8xJaftn9Ggw&feature=youtu.be) você vai ver como foi o passo que seguimos para realizar essa tarefa
