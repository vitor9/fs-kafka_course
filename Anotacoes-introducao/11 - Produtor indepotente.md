# 11 - Produtor indepotente

## Producer: Indepotência

![570A7ED7-1925-4CB2-BA34-6CA3FF8DF9F4.jpeg](11%20-%20Produtor%20indepotente%20e2830856dc2340509204c3757e9cf14e/570A7ED7-1925-4CB2-BA34-6CA3FF8DF9F4.jpeg)

### Produtor com indepotência OFF

Não vai se importar se durante uma indisponibilidade que afetou o ack da msg e duplicou a msg que ficou na fila.

Ele vai gravar a msg duplicada e o consumer vai ler a msg 2x.

O Kafka vai entender que o produtor mandou a msg 2x.

### Produtor com indepotência ON

Descarta a mensagem duplicada

O Kafka vai saber que houve disponibilidade e vai descartar essa msg duplicada.

Gera mais lentidão, mas o Kafka consegue descartar e simultaneamente que a msg caia na ordem correta, por conta dos timestamps.