# Gerando uma cobrança via Pix para QR Code

## Necessidades

Nosso sistema precisa permitir que os usuários possam gerar cobranças de pagamento via Pix e que estas possam ser compartilhadas com praticidade através de **QR Code**, dessa forma as cobranças poderão ser com amigos e familiares e, após o pagamento, o dinheiro cairá imediatamente na conta dos nossos usuários. Apesar de nosso sistema não ser o responsável por gerar a imagem de QR Code em si, ele deverá gerar os **metadados** que estarão contidos nas imagens.

Quando falamos de cobrança via QR Code, precisamos lembrar que o Banco Central (BCB) diferencia um QR Code em dois tipos: dinâmico e estático. A grande diferença entre eles está no número de transações que podem ser realizadas usando o QR Code – o estático pode ser usado para diversos pagamentos de um mesmo valor, enquanto o dinâmico vale apenas para uma única transação.

Vamos entender um pouco mais sobre a diferença de ambos:

**QR Code estático**

O QR Code estático pode ser usado para diversas transações e, segundo o Banco Central, permite:

- Que o recebedor defina um valor fixo para um produto ou cobrança;
- E também a inserção de um valor pelo pagador;

Na prática, um QR Code estático é como uma etiqueta de preço único. Ele não muda, e você pode usar ele para cobrar o mesmo valor de várias pessoas. Ele é, portanto, mais flexível. A recomendação do BC é de que ele é mais apropriado pra pessoas físicas, pequenos varejistas e prestadores de serviços.

**QR Code dinâmico**

Diferente do anterior, o QR Code dinâmico é exclusivo para cada transação. Isso significa que **ele só pode ser usado uma vez**, ou seja, para fazer uma segunda cobrança usando um QR Code, é necessário gerar um novo.

Além disso, também é possível incluir outros dados e informações no QR Code, como a identificação detalhada do recebedor, tempo de expiração do QR Code, data de vencimento, juros, multas e descontos, entre outras.

Por ser exclusivo para cada transação e gerado por um sistema, a expectativa é de que este tipo de QR Code seja mais usado em compras online, por e-commerces, ou cobranças mais formais.

Nesta primeira fase do lançamento do Pix, nós implementaremos uma versão simplificada de cobrança via Pix através de QR Code, somente com os metadados suficientes para que uma transação ocorra de forma eficiente e segura.
   
## Restrições

Para gerar uma cobrança via Pix, precisamos que o usuário informe os seguintes dados:

- **Chave Pix** é obrigatória;
- **Tipo de cobrança** é obrigatório, e pode ser:
  - Dinâmica;
  - Estática;

- **Valor da cobrança** possui precisão de 2 casas decimais e:
  - Quando tipo da cobrança for dinâmico, o valor será obrigatório;
  - Quando tipo da cobrança for estático, o valor será opcional (o usuário poderá informar no momento do pagamento);
  
- **Descrição da cobrança** é opcional e deve contar máximo de 100 caracteres;

## Resultado Esperado

- Em caso de sucesso, deve-se gerar uma cobrança no sistema e retornar os seguintes metadados:
  - **ID da cobrança**: obrigatório e único;
  - **Tipo de cobrança**: obrigatório e pode assumir os valores:
    - Estático;
    - Dinâmico;
  - **Chave Pix do recebedor**: obrigatória;
  - **Informações do recebedor**: obrigatório, com:
    - Nome completo;
    - CPF (formato `999.999.999-99`);
    - Instituição financeira;
  - **Data e hora de criação**: obrigatório;
  - **Valor da cobrança**:
    - Quando tipo de cobrança for dinâmico, este campo será obrigatório;
    - Quando tipo de cobrança for estático, este campo será opcional (pagador pode informar no ato do pagamento);

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

- Sentir-se confortável com o negócio é importante, afinal como resolver um problema sem entendimento do domínio, não é mesmo? Portanto, recomendamos a leitura dos artigos para entender um pouco mais sobre o Pix e sua modalidade de cobranças via QR Code:
  - [Apresentação do Pix pelo Banco Central (BCB)](https://www.bcb.gov.br/conteudo/home-ptbr/TextosApresentacoes/Apresentacao_PIX.pdf)
  - [Pix: qual a diferença entre o QR Code estático e QR Code dinâmico?](https://blog.nubank.com.br/pix-qr-code-estatico-dinamico/)
  - [Pix: QR Code Estático X QR Code Dinâmico](https://blog.juno.com.br/pix-qr-code-estatico-x-qr-code-dinamico/)
  - [BC lança novas funcionalidades do Pix para emissão de QR Code](https://www.ecommercebrasil.com.br/noticias/bc-novas-funcionalidades-pix-qr-code/)

## Sugestões de busca de conteúdo