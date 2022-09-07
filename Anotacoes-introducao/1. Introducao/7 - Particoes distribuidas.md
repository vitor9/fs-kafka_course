# 7 - Partições distribuídas

Em um cenário normal, cada vez que o nosso tópico/producer manda uma msg, ela pode cair em alguma dessasa partições dos brokers.

Cada Broker eh uma maquina totalmente diferente, e essas partições ficam separadas. Partição fica em disco, com segmentos em mensagens para serem guardadas.

Imaginando agora a seguinte situação…

Se um Broker caisse, iamos perder as mensagens de alguma dessas partições.

![372546A8-2C02-41E2-92A4-62F448187E9F.jpeg](7%20-%20Partic%CC%A7o%CC%83es%20distribui%CC%81das%20c6c8efabfed44b18b5441327536c48a2/372546A8-2C02-41E2-92A4-62F448187E9F.jpeg)

O Kafka nos disponibiliza o Replicator Factor para isso, aonde é feito uma cópia/réplica em outros Brokers, ele consegue nos garantir resiliencia.

![8B889E9E-3950-44C3-99B0-8BE4C625B398.jpeg](7%20-%20Partic%CC%A7o%CC%83es%20distribui%CC%81das%20c6c8efabfed44b18b5441327536c48a2/8B889E9E-3950-44C3-99B0-8BE4C625B398.jpeg)

As partições ficam distribuidas, mas conseguimos fazer uma cópia.

Um exemplo, Replicator = 4.

Vou ter 10 partiçõese, mas com os meus brokers , vou ter que ter 4 cópias dessas partições separadas nos brokers. Não é por Broker, e sim, pela quantidade especificada, seja lá qual for a quantidade de maquinas.

Quanto maior o replicator factor, maior o espaço em disco e consumo do Broker.

Normalmente, utilizam 2 ou 3 Replicator Factors