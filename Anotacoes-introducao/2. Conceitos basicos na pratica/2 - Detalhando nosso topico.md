# 2 - Detalhando nosso topico

Novamente listando os comandos do Kafka, podemos ver um outro comando chamado de:

“—describe”

```bash
kafka-topics --bootstrap-server=localhost:9092 --topic=teste --describe
```

Detalhamos nosso topico dessa forma, conseguimos entender melhor como nosso topico funciona.

Quando estou criando um topico, também escolho o meu ReplicationFactor

Sempre ter em mente, o topico, ele tem:

- As partições lideres
- Quantas replicas
- Qual o replicationFactor