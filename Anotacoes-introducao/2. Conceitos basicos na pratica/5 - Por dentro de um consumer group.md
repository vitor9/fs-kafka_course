# 5 - Por dentro de um consumer group

Como consigo ver no meu consumer-group, cada consumidor que está conectado e o que ele está lendo?

Podemos descrever isso tudo rodando o seguinte comando:

```bash
kafka-consumer-groups --bootstrap-server=localhost:9092 --group=x --describe
```

Essa é a saida

```bash
GROUP           TOPIC           PARTITION  CURRENT-OFFSET  LOG-END-OFFSET  LAG             CONSUMER-ID                                       HOST            CLIENT-ID
x               teste           0          4               4               0               consumer-x-1-2247e8d0-e52a-4568-82ea-20628d8ceb49 /172.18.0.3     consumer-x-1
x               teste           1          4               4               0               consumer-x-1-2247e8d0-e52a-4568-82ea-20628d8ceb49 /172.18.0.3     consumer-x-1
x               teste           2          6               6               0               consumer-x-1-5ffaac1b-6283-40ea-b7cc-edd6ef10255a /172.18.0.3     consumer-x-1
```

- current-offset - Offset atual que esta sendo lido
- log-end-offset - a posicao final que ira se encerrar a sequencia de offset do topico
- lag - eh a diferença entre o current e o log-end offsets.
- consumer-id - sao os consumers que estamos conectados no momento.
    - Observação: podemos ver que de fato, os consumidores de ID final “b49”, estão lendo 2 partições(partts 0 e 1). Por isso eles reproduzem primeiro mais mensagens do que o seu outro consumidor(com ID final 55a lendo a partt 2)