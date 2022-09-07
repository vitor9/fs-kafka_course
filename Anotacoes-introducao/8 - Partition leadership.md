# 8 - Partition leadership

Temos uma cópia, mas como ficaria a alta disponibilidade do Broker/Partições

![B0068A8A-D6CC-4E47-B203-6610CCA5295A.jpeg](8%20-%20Partition%20leadership%20b6c3fb7263814f1c915e4c6af01cf511/B0068A8A-D6CC-4E47-B203-6610CCA5295A.jpeg)

No Kafka, temos uma funcionalidade chamada de Partition Leadership(Liderança das Partições).

Necessariamente o consumidor vai ler a partição líder.

E se o Broker A cair, ele procurar por outro Broker com aquela partição que foi denominada líder naquele Broker, que nesse caso é a partição 1

![B45735E0-1F27-41FB-913F-25088EB96BDA.jpeg](8%20-%20Partition%20leadership%20b6c3fb7263814f1c915e4c6af01cf511/B45735E0-1F27-41FB-913F-25088EB96BDA.jpeg)