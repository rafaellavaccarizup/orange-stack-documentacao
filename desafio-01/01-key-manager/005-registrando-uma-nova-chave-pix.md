# Registrando uma nova chave Pix

## Necessidades

Nosso usuário precisa registrar (cadastrar) uma nova chave Pix para que ele possa gerar cobranças e efetuar pagamentos de cobranças na nossa plataforma.
   
## Restrições

Para registrar uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Tipo da chave** deve ser obrigatório, e pode ser:
    - CPF;
    - telefone celular;
    - email;
    - chave aleatória;

- **Valor da chave** deve ser obrigatório, válido e único:
    - Quando tipo for CPF, usar formato `999.999.999-99`;
    - Quando tipo for telefone celular, usar formato `(99) 99999-999`;
    - Quando tipo for email, deve ser um endereço válido;
    - Quando tipo for chave aleatória, deve-se informar um apelido (alias) para a chave, pois a chave em si será gerada pelo sistema;

- **Tipo de conta** associada a chave Pix deve ser obrigatória, e pode ser:
    - Conta Corrente;
    - Conta Poupança;

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser registrada e armazenada no sistema;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo