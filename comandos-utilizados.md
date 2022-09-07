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

Ira ler as msgs do topico desde o offset 0, caso coloquemos o parametro "--from-beginning".

```bash
kafka-console-producer --bootstrap-server=localhost:9092 --topic=teste --from-beginning
```

