# Comandos utilizados ao longo do curso

## Subind o ambiente

```bash
docker-compose up -d
```

## Podemos entrar dentro do nosso container kafka, utilizando o seguinte comando

```bash
docker exec -it fs-kafka_course_kafka_1 bash
```

## Rodamos o seguinte comando para criar o nosso topico

```bash
kafka-topics --create --topic=teste --bootstrap-server=localhost:9092 --partitions=3
```

## Listamos os topicos da seguinte maneira

```bash
kafka-topics --list --bootstrap-server=localhost:9092
```

## Detalhando nosso topico

```bash
kafka-topics --bootstrap-server=localhost:9092 --topic=teste --describe
```

## Configurando um consumer

```bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste
```

## Configurando um producer

- Ira ler as msgs do topico desde o offset 0, caso coloquemos o parametro "--from-beginning".
- Add o consumer a um grupo chamado x, com o parametro "--group=x"
  
```bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --from-beginning --group=x
```

## Detalhando o nosso grupo de consumers

- current-offset - Offset atual que esta sendo lido
- log-end-offset - a posicao final que ira se encerrar a sequencia de offset do topico
- lag - eh a diferença entre o current e o log-end offsets.

```bash
kafka-consumer-groups --bootstrap-server=localhost:9092 --group=x --describe
```

## Link para o Confluent Control Center

[Clusters](localhost:9021/clusters)

## Mantendo do container log aberto e atualizando a cada 10 segs

docker logs -f --tail 10 2-desenv-produtor_consumidor_kafka_1

## Puxando as dependencias do Go

go mod init github.com/vitor9/fc2-gokafka