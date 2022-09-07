# 1 - Criado primeiro tópico

Internamente, o Kafka possui toda uma interface de comunicação.

A gente pode “acessar” o kafka, tanto pelas apps que a gente desenvolve, quanto pela linha de comando

Podemos entrar dentro do nosso container kafka, utilizando o seguinte comando

```bash
	docker exec -it kafka_kafka_1 bash
```

ao entrar no container, se digitarmos “kafka” e dar tab para auto-completar, vamos notar varias sugestões de comandos do Kafka.

Um desses comandos que vamos utilizar para criar os nossos tópicos, que é o kafka-topics.

Temos também o “kafka-console-consumer” e o “kafka-console-producer”

Toda hora que formos criar algo no Kafka ou vamos trabalhar na linha de comando, precisamos passar o parametro: —bootstrap-server. Ele basicamente eh o servidor que vou utilizar para trabalhar com o Kafka. Ele é **required**.

Outro comando também, é o “—create”. Ele vai ajudar e falar que iremos querer criar um novo tópico.

Também tem o “—partitions”, aonde falamos o numero de partições que vamos trabalhar.

Tem o “—topic” que vamos também passar.

Enfim, rodamos o seguinte comando para criar o nosso topico

```bash
kafka-topics --create --topic=teste --bostrap-server=localhost:9092 --partitions=3
```

Detalhe, na porta passamos a mesma que especificamos no arquivo yaml

Listamos o topico da seguinte maneira:

```bash
kafka-topics --list --bootstrap-server=localhost:9092
```

Ao listar, um retorno com varios topicos, um deles, o “__consumer_offsets”

Aqui é aonde o Kafka guarda qual offset determinado consumer esta na leitura dos topicos.

Se está sendo feito uma leitura e acaba por algum motivo interrompendo a leitura, ele é responsável por colocar de volta aonde a leitura foi interrompida.