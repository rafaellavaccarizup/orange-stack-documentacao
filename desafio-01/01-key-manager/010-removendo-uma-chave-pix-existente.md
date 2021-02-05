# Removendo uma chave Pix existente

## Necessidades

Nosso usuário precisa excluir suas chaves Pix cadastradas, pois dessa forma, se necessário, ele poderá recriar uma chave associada à uma nova conta corrente ou poupança.
   
## Restrições

Para excluir uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Pix ID** (idenficiador interno da chave Pix) deve ser obrigatório;

- **Identificador do cliente** deve ser obrigatório:
   - Código interno do cliente na Instituição Financeira existente no [Sistema ERP do Itaú](http://localhost:9091/api/v1/private/contas/todas);

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser excluída do sistema;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

- Os dados do cliente e de sua conta corrente **devem ser obtidos do [Sistema ERP do Itaú](http://localhost:9091/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/)**; 

## Sugestões de busca de conteúdo
