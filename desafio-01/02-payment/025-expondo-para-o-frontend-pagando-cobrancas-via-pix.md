# Expondo para o frontend: Pagando cobranças via Pix

## Necessidades

Agora, o frontend precisa permitir que nosso usuário possa ler imagens QR Code de cobranças para que em seguida ele consiga efetuar o pagamento da mesma. Portanto, devemos expor em nossa API REST a operação de [pagamento de cobranças via Pix](010-pagando-uma-cobranca-via-pix.md).
   
## Restrições

Para efetuar o pagamento de uma cobrança via Pix, precisamos que o usuário informe os dados necessários para esta finalidade (que será obtido a partir do QR Code). Você pode levantar essas informações com detalhes a partir da [atividade de pagamento de cobranças via Pix que implementamos no módulo Payment gRPC](010-pagando-uma-cobranca-via-pix.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

## Resultado Esperado

- Em caso de sucesso, a cobrança deve ser liquidada no sistema e por fim retornar os dados de confirmação do pagamento;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo