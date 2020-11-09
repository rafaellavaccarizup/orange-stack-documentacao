# Expondo para o frontend: Gerando cobranças via Pix para QR Code

## Necessidades

Nosso frontend precisa gerar cobranças via Pix para QR Code para que o usuário possa compartilhar suas cobranças com amigos e familiares. Portanto, a primeira funcionalidade que iremos expor via nossa API REST é justamente a operação para [gerar uma cobrança via Pix](005-gerando-uma-cobranca-via-pix-para-qrcode.md).
   
## Restrições

Para gerar uma cobrança via Pix, precisamos que o usuário informe os dados necessários para esta finalidade. Você pode levantar essas informações com detalhes a partir da [atividade de geração de cobranças via Pix para QR Code que implementamos no módulo Payment gRPC](005-gerando-uma-cobranca-via-pix-para-qrcode.md).

Lembre-se de seguir as boas práticas de design de APIs REST, pois o time de mobile leva isso em consideração.

Por questões de segurança, o CPF do recebedor deve ser **obfuscado** antes de embuti-lo na imagem do QR Code. Portanto, nossa API REST deve obfuscá-lo e retorná-lo no seguinte formato `999.xxx.xxx-99`.

## Resultado Esperado

- Em caso de sucesso, a cobrança via Pix deve ser gerada, armazenada no sistema e por fim retornar os dadosnecessários que serão utilizados para gerar o QR Code no dispositivo mobile;

- Em caso de erro, deve-se retornar o erro específico e amigável para o usuário final;

## Informações de suporte

## Sugestões de busca de conteúdo