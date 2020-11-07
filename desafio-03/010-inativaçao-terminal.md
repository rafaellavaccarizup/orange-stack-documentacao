# Inativação de um Terminal

## Contexto

Algumas restrições se aplicam ao terminal quando há quebra de contrato ou quando não há pagamento das taxas
relativas as transações realizadas naquele terminal.

Neste caso precisamos realizar uma inativação daquele terminal de modo que o dono do terminal não esteja mais 
apto a realizar transações.

## Objetivo

Realizar a inativação de um terminal no sistema.

## Restrições

- Identificador do terminal é obrigatório na URL.

- Devemos seguir as boas práticas de integração utilizada.

## Resultado Esperado

- Em caso de sucesso:
   
   - O terminal deve estar bloqueado no sistema para fazer novas transações.

   - Deve ser retornado o **HTTP Status 200**
    
- Em caso de erro, deve ser retornado o erro específico:

    - Retornar **HTTP Status 404** quando não encontrado o terminal.
    
    - Retornar **HTTP Status 500** quando ocorrer um erro inesperado.
    
## Informações de suporte

## Sugestões de busca de conteúdo