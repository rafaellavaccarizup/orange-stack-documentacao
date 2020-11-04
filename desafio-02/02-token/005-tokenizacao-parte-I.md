# Tokenização - Parte I

## Necessidades

Precisamos desenvolver uma funcionalidade de **tokenização** que recebe os dados do(a) portador(a) do cartão e gerar 
um **token único** que representa o cartão para aquele parceiro\canal de compra.

## Restrições

Devemos receber os seguintes dados:

- Nome do(a) portador(a) do cartão deve ser obrigatório.
- CPF do(a) portador(a) do cartão deve ser obrigatório.
- Número do cartão deve ser obrigatório.
- Data de expiração do cartão no formato MMYY deve ser obrigatório.
- Código de verificação (CVV) do cartão deve ser obrigatório.

Devemos armazenar os seguintes dados:

- Todos os dados que recebemos na requisição
- A hora e data em UTC da operação

**Lembre-se** devemos utilizar as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso, o token deve ser armazenado no sistema, com um identificador gerado pelo sistema não sequencial.

- Em caso de erro, deve ser retornado o erro específicos.

## Informações de suporte

## Sugestões de busca de conteúdo