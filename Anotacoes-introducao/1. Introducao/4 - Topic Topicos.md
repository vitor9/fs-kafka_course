# 4 - Topic/Tópicos

> Tópico é o canal de comunicação responsável por receber e disponibilizar os dados enviados para o Kafka
> 

Tópico é o local aonde é enviado as msgs

Quando o Produtor envia uma msg para o broker, essa msg é enviada para um tópico.

Se um consumidor quer ler as msgs, ele vai ler a msg de um tópico.

![D724F885-F411-4FE9-A006-33432391A09A.jpeg](4%20-%20Topic%20To%CC%81picos%20a93bc0d566e741b0a25f7e5700620c75/D724F885-F411-4FE9-A006-33432391A09A.jpeg)

Posso ter varios sistemas diferentes lendo um tópico.

As “msgs” podem ser lidas por vários consumidores.

Tópico é mais ou menos como se fosse um log

Log basicamente é um local aonde é armazenado diversas informações.

![3E35AC33-EFEE-4C63-A04A-E48D39770E75.jpeg](4%20-%20Topic%20To%CC%81picos%20a93bc0d566e741b0a25f7e5700620c75/3E35AC33-EFEE-4C63-A04A-E48D39770E75.jpeg)

Cada msg que o produtor enviar para o tópico, ela vai sendo armazenada uma atrás da outra.

O Kafka salva em disco essas mensagens, para serem lidas e relidas, por um ou mais sistemas.

Quando armazenada, ela ganha uma espécie de “id”. Temos um offset, a posição basicamente aonde esta cada msg.

Na imagem acima, o primeiro offset é o 0.

Um consumidor pode estar lendo a msg 6, outro pode estar lendo a msg 7. Neste mesmo momento, está sendo add uma nova msg no final do log.

Ou seja, não tem problema se um consumidor estiver mais adiantado que o outro na leitura dessas msgs, pois o Kafka vai estar produzindo novas msgs normalmente.

O Kafka permite que reprocessemos essas msgs, como se fosse “rebobinar uma fita”, para ler novamente a msg.