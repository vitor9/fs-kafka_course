# 3 - Consumindo e produzindo mensagens

Precisamos agora entender como o Kafka consume e produz mensagens

O comando “kafka-console-consumer”:

```bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste
```

É responsável por começar a consumir um tópico.

Os parametros do comando

- “—group “ nos ajuda a agrupar diversos consumidores para nosso processo de leitura.
- “—from-beginning” - Faz ler a partir das novas mensagens que vão chegando para processar. Por padrão é desativado. Ao especificarmos esse parametro, ele começa a ler do “offset 0”

Vamos agora configurar o nosso producer.

```bash
kafka-console-producer --bootstrap-server=localhost:9092 --topic=teste
```

Configuramos o nosso producer para produzir mensagens para o nosso topico “teste”, criado anteriormente.

Da forma que criamos o consumidor, ele não vai consumir as msg se o comando não tiver sido executado, ele não escuta as msg produzidas enquanto nao executar o comando.

Ele não perde as msg, ele começa a ler daonde o producer começa a mandar as msgs para a gente.

Para lermos apartir do começo, colocamos aquele parametro “—from-beggining” 

```bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --from-beginning
```

As msg que produzimos enquanto não havia sido executado o comando irão aparecer, porem **fora de ordem**

Isso acontece porque cada msg foi para uma particao diferente. Na hora que for ativado o consumer, ele vai sair lendo particao por particao e vai mostrando de acordo com o que ele leu.

Nao garantimos a ordem das msg, soh **garantimos a ordem das msgs com as Keys**.

Assim, garantimos que a msg foi para a mesma particao, garantindo a ordem delas.