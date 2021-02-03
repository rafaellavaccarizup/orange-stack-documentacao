# Registrando uma nova chave Pix

## Necessidades

Nosso usuário precisa registrar (cadastrar) uma nova chave Pix para que ele possa gerar cobranças e efetuar pagamentos de cobranças na nossa plataforma.
   
## Restrições

Para registrar uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Identificador do cliente** deve ser obrigatório (código interno do cliente na Instituição Financeira);

- **Tipo da chave** deve ser obrigatório, e pode ser:
    - CPF;
    - telefone celular;
    - email;
    - chave aleatória;

- **Valor da chave** deve ser obrigatório, válido e único:
    - Quando tipo for CPF, usar formato `^[0-9]{11}$` (por exemplo: `12345678901`);
    - Quando tipo for telefone celular, usar formato `^\+[1-9][0-9]\d{1,14}$` (por exemplo: `+5585988714077`);
    - Quando tipo for email, deve ser um endereço válido com tamanho máximo de 77 caracteres;
    - Quando tipo for chave aleatória, deve-se informar um valor seguindo o [formato UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier);

- **Tipo de conta** associada a chave Pix deve ser obrigatória, e pode ser:
    - Conta Corrente;
    - Conta Poupança;

## Resultado Esperado

- Em caso de sucesso, a chave Pix deve ser registrada e armazenada no sistema;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo
