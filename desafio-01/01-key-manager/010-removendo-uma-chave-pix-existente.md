# Removendo uma chave Pix existente

## Necessidades

Nosso usuário precisa excluir suas chaves Pix cadastradas, pois dessa forma ele poderá recriar uma chave associada à uma nova conta corrente ou poupança.
   
## Restrições

Para excluir uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Tipo da chave** deve ser obrigatório, e pode ser:
    - CPF;
    - telefone celular;
    - email;
    - chave aleatória;

- **Valor da chave** deve ser obrigatório:
    - Quando tipo for CPF, usar um CPF existente;
    - Quando tipo for telefone celular, usar um número existente;
    - Quando tipo for email, usar um email existente;
    - Quando tipo for chave aleatória, usar um apelido (alias) existente;


## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser excluída do sistema;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo