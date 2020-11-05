# Consultando os dados de uma chave Pix

## Necessidades

Precisamos disponibilizar um meio de consultar os dados de uma determinada chave Pix, dessa forma outros serviços e sistemas poderão exibir as informações da chave (nome e CPF do titular, banco, agência etc) para seus usuários ou mesmo para validá-las.
   
## Restrições

Para consultar uma chave Pix, precisamos que os seguintes dados sejam informados:

- **Chave Pix** deve ser obrigatório;

Caso a chave Pix não esteja devidamente [registrada no BCB](015-registrando-e-excluindo-chaves-pix-no-bcb.md), a mesma não poderá ter suas informações disponibilizadas abertamente, afinal trata-se de uma chave ainda inválida.

No caso de nosso sistema **não possuir** a chave Pix informada, a mesma deve ser consultada no [sistema Pix do BCB](015-registrando-e-excluindo-chaves-pix-no-bcb.md).

## Resultado Esperado

- Em caso de sucesso, deve-se retornar os dados da chave Pix:
  - Tipo da chave;
  - Valor da chave;
  - Nome completo do titular da conta;
  - CPF do titular da conta (formato `999.999.999-99`);
  - Instituição financeira (nome do banco, da fintech etc);
  - Dados da conta: agência, número da conta e tipo da conta (corrente ou poupança);

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo