# 5 - Partições

Vamos entender agora o registro que é armazenado por esses produtores

## Anatomia de um registro

![A586EA25-E7C0-4617-BC98-F612AB3BA7F7.jpeg](5%20-%20Partic%CC%A7o%CC%83es%20ace0581463cb42f799a874d49df7e97c/A586EA25-E7C0-4617-BC98-F612AB3BA7F7.jpeg)

Um offset é composto por 4 partes principais:

- Headers
    - Podem ser metadados úteis no processo. Não são obrigatórios.
- Keys
    - Um contexto sobre o agrupamento de msgs, para a ordem da entrega.
- Value
    - Conteúdo em JSON
- Timestamp

## Partições

> Cada tópico pode ter uma ou mais partições para conseguir garantir a distribuição e resiliência de seus dados
> 

![5FA3053C-DA00-418B-8ADD-95D65960DC61.jpeg](5%20-%20Partic%CC%A7o%CC%83es%20ace0581463cb42f799a874d49df7e97c/5FA3053C-DA00-418B-8ADD-95D65960DC61.jpeg)

Sempre que um tópico manda uma msg, essa msg vai para uma partição. Essa partição está em Broker A, p/ex.

Se uma partição ficar indisponível, o tópico pode envia-las para as outras partições disponiveis.

Toda vez que aumentamos a quantidade de partição, as msgs ficam mais separadas.

Podemos fazer que, um sistema que tenha mais de um Broker, faça a leitura de tópicos diferentes, separando as msgs para máquina diferentes.

Com isso, vamos ter mais desempenho na leitura de msgs, porque vários brokers vão estar fazendo a leitura simultaneamente, ao invés de 1 só ter que fazer a leitura de todas elas.

3 máquinas, para 3 partições, é processado a leitura 3x mais rápido por exemplo, tem um desempenho muito melhor que 2 para 2 ou, 1 só máquina para mais de 1 partição.

Ou seja, o beneficio disso tudo, é que fica mais distribuido as msgs, mas ao mesmo tempo, permitimos que tenhamos mais consumidores consumindo o mesmo tópico, pq as msgs desses tópicos estão separadas em diferentes partições.

Por isso é bastante escalável o Kafka.

Quando formos criar um tópico, vamos ter que falar quantas partições esse tópico vai ter. E ai, cada hora a msg vai cair em partição diferente.