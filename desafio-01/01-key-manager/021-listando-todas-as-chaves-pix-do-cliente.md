# Listando todas as chaves Pix do cliente

## Necessidades

Agora, precisamos consultar todas as suas chaves Pix cadastradas. Para isso, precisamos listar todas as chaves de um determinado cliente.
   
## Restrições

Para listar todas as chaves Pix cadastradas, precisamos que o usuário informe os seguintes dados:

- **Identificador do cliente** deve ser obrigatório:
   - Código interno do cliente na Instituição Financeira existente no [Sistema ERP do Itaú](http://localhost:9091/api/v1/private/contas/todas);

## Resultado Esperado

- Em caso de sucesso, deve-se todas as chaves Pix com os seguintes dados:
  - Pix ID;
  - Identificador do cliente;
  - Tipo da chave;
  - Valor da chave;
  - tipo da conta (Corrente ou Poupança);
  - Data/hora de registro ou criação da chave;

- Se nenhuma chave for encontrada deve-se retornar uma coleção vazia;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte
- Tem dúvidas em como criar um endpoint para listagem? [Neste vídeo](https://www.youtube.com/watch?v=PML9YWZUnbk&feature=youtu.be) você pode conferir sobre como realizar uma listagem com Micronaut e JPA
- Quer saber como fazer uma query Micronaut Data? [Esse vídeo](https://www.youtube.com/watch?v=cph_Ei7tulY&feature=youtu.be) pode te ajudar a como criar essa query no repositório

## Como nós implementamos
Quer saber como nós da Zup Edu implementamos esse serviço? [Neste vídeo](https://www.youtube.com/watch?v=YSLGHdvOvDw&feature=youtu.be) Você vai ver como foi o passo que seguimos para realizar essa tarefa
