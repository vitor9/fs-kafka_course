# 3 - Dinâmica de Funcionamento

## Conceitos e dinâmica básica de funcionamento

![F5EA1EFC-23C0-48FE-97F3-4E2D249C836E.jpeg](3%20-%20Dina%CC%82mica%20de%20Funcionamento%202be81d6436df420d8fc8340f289a99b0/F5EA1EFC-23C0-48FE-97F3-4E2D249C836E.jpeg)

Producer - Quem produz um evento

Consumer - Quem quer consumir o conteúdo desse evento

O Kafka serve como um intermediário entre esses dois sistemas

Kafka é um conjunto de maquinas, um cluster.

Um Cluster é formado de nós, chamamos os nós de cluster de brokers.

Quando falamos de Kafka, falamos do Kafka Broker, que são as máquinas que conseguem armazenar processar e armazenar os nossos eventos.

O Producer pega a msg, manda para o Kafka, ela vai cair em um Broker e vai ficar guardado em um banco de dados.

Cada Broker tem o seu banco de dados.

O consumidor acessa o Kafka broker e lê esse banco de dados e pega essa informação.

O Kafka não envia nenhuma msg para ninguém. Ele guarda ela para que o consumidor leia.

Para colocar um cluster em produção do Kafka, a recomendação minima são 3 máquinas, ou 3 brokers(como o exemplo da img)

Os Brokers se comunicam o tempo inteiro.

O Kafka precisa de um sistema que gerencie todo esse processo de comunicação entre os Brokers. Por exemplo: como é feito as prioridades, como sabe qual máquina tá online ou não.

Existe um outro projeto da Apache chamada de Zookeeper. Ele é um sistema de service discovery que faz bastante coisa, uma delas é auxiliar o Kafka com a comunicação entre os Brokers.

O Zookeeper está de saída, o Kafka quer a sua indepêndencia e quer deixar toda a responsabilidade para o Kafka mesmo.