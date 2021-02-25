# Expondo para o frontend: Remoção de uma chave Pix existente

## Necessidades

Dessa vez, nosso frontend precisa permitir que seu usuário consiga excluir suas chaves Pix cadastradas diretamente do aplicativo mobile, desse modo ele poderá substituir as chaves sempre que necessário. Portanto, devemos expor em nossa API REST a [operação de exclusão de chaves](010-removendo-uma-chave-pix-existente.md).
   
## Restrições

Para excluir uma chave Pix existente, precisamos que o usuário informe os dados necessários para tal. Você pode levantar essas informações com detalhes a partir da [atividade de remoção de chaves Pix que implementamos no módulo Key-Manager gRPC](010-removendo-uma-chave-pix-existente.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser excluída do sistema;

- Em caso de chave não encontrada, deve-se retornar status de erro `404-NOT_FOUND` com uma mensagem amigável para o usuário;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo