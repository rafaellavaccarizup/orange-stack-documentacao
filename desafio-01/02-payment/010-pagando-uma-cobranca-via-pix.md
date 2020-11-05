# Pagando uma cobrança via Pix

## Necessidades

Agora, precisamos efetuar o pagamento de cobranças via Pix que foram compartilhadas através de QR Code. Nosso sistema não será responsável por ler o QR Code, mas somente lidar com os metadados extraídos da imagem.

Um detalhe importante, até este momento a especificação da API de cobranças do Pix que será utilizada pelos bancos ainda não foi concluída pelo Banco Central (BCB), portanto, nesta primeira fase de lançamento do Pix, suportaremos apenas cobranças QR Code geradas pela nossa própria plataforma. Ou seja, os QR Codes que **seguem o formato (schema) esperado dos metadados** definido por nós. Em um futuro não distante, aceitaremos outros QR Codes com formatos diferentes gerados por outras instituições financeiras e fintechs.
   
## Restrições

Para efetuar o pagamento de uma cobrança via Pix, precisamos dos seguintes dados:

- **ID da cobrança** é obrigatório;
- **Chave Pix do pagador (origem)** é obrigatória;
- **Chave Pix do recebedor (destino)** é obrigatória;
- **Tipo de cobrança** é obrigatório e pode assumir os valores: dinâmico e estático;
- **Valor da cobrança** é obrigatório;

Para o caso de cobrança dinâmica, o sistema deve:
  - garantir que a cobrança seja liquidada somente **uma única vez**.
  - garantir que o valor liquidado seja exatamente **o mesmo** configurado na cobrança;

## Resultado Esperado

- Em caso de sucesso, deve-se liquidar a cobrança no sistema e retornar os seguintes dados de confirmação:
  - **ID da transação**: obrigatório e único;
  - **Informações do pagador (origem)**: obrigatório, com:
    - Chave Pix;
    - Nome completo;
    - CPF (formato `999.999.999-99`);
    - Instituição financeira;
  - **Informações do recebedor (destino)**: obrigatório, com:
    - Chave Pix;
    - Nome completo;
    - CPF (formato `999.999.999-99`);
    - Instituição financeira;
  - **Data e hora do pagamento**: obrigatório;
  - **Valor pago**: obrigatório;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo