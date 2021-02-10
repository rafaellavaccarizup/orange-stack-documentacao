# Consultando os dados de uma chave Pix

## Necessidades

Precisamos disponibilizar um meio de consultar os dados de uma determinada chave Pix, dessa forma outros serviços e sistemas poderão exibir as informações da chave (nome e CPF do titular, banco, agência etc) para seus usuários ou mesmo para validá-las.
   
## Restrições

Para consultar uma chave Pix, precisamos que os seguintes dados sejam informados:

- **Identificador do cliente** deve ser obrigatório:
   - Código interno do cliente na Instituição Financeira existente no [Sistema ERP do Itaú](http://localhost:9091/api/v1/private/contas/todas);
   
- **Pix ID** ou **Chave Pix** deve ser obrigatória;

Caso a chave Pix não esteja devidamente [registrada no BCB](015-registrando-e-excluindo-chaves-pix-no-bcb.md), a mesma não poderá ter suas informações disponibilizadas abertamente, afinal trata-se de uma chave ainda inválida.

No caso de nosso sistema **não possuir** a chave Pix informada, a mesma deve ser consultada no [sistema Pix do BCB](015-registrando-e-excluindo-chaves-pix-no-bcb.md).

## Resultado Esperado

- Em caso de sucesso, deve-se retornar os dados da chave Pix:
  - Pix ID (opcional);
  - Identificador do cliente (opcional);
  - Tipo da chave;
  - Valor da chave;
  - Nome e CPF do titular da conta;
  - Dados da conta vinculada a chave Pix:
    - nome da instituição financeira;
    - agência, número da conta e tipo da conta (Corrente ou Poupança);
  - Data/hora de registro ou criação da chave;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo
