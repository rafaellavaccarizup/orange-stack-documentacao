# Registrando uma nova chave Pix

## Necessidades

Nosso usuário precisa registrar (cadastrar) uma nova chave Pix para que ele possa gerar cobranças e efetuar pagamentos de cobranças na nossa plataforma.
   
## Restrições

Para registrar uma chave Pix, precisamos que o usuário informe os seguintes dados:

- **Identificador do cliente** deve ser obrigatório:
   - Código interno do cliente na Instituição Financeira existente no [Sistema ERP do Itaú](http://localhost:9091/api/v1/private/contas/todas);

- **Tipo da chave** deve ser obrigatório, e pode ser:
    - CPF;
    - telefone celular;
    - email;
    - chave aleatória;

- **Valor da chave** deve ser válido e único com tamanho máximo de 77 caracteres:
    - Quando tipo for CPF, deve ser obrigatório e usar formato `^[0-9]{11}$` (por exemplo: `12345678901`);
    - Quando tipo for telefone celular, deve ser obrigatório e usar formato `^\+[1-9][0-9]\d{1,14}$` (por exemplo: `+5585988714077`);
    - Quando tipo for email, deve ser obrigatório e um endereço válido;
    - Quando tipo for chave aleatória, o valor da chave **não** deve ser preenchido (não se preocupe, veremos como gerar essa chave um pouco mais à frente);

- **Tipo de conta** associada a chave Pix deve ser obrigatória, e pode ser:
    - Conta Corrente;
    - Conta Poupança;

## Resultado Esperado

- Em caso de sucesso:
   - a chave Pix deve ser registrada e armazenada no sistema;
   - deve-se retornar um ID interno ("pix ID") para representar a chave Pix criada pelo sistema;

- Em caso de erro, deve-se retornar o erro específico;

## Informações de suporte

- Os dados do cliente e de sua conta corrente **devem ser obtidos do [Sistema ERP do Itaú](http://localhost:9091/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/)**; 

## Sugestões de busca de conteúdo
