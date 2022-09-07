# Podemos entrar dentro do nosso container kafka, utilizando o seguinte comando

```bash
docker exec -it kafka_kafka_1 bash
```

Enfim, rodamos o seguinte comando para criar o nosso topico

```bash
kafka-topics --create --topic=teste --bostrap-server=localhost:9092 --partitions=3
```

Listamos o topico da seguinte maneira:

```bash
kafka-topics --list --bootstrap-server=localhost:9092
```
