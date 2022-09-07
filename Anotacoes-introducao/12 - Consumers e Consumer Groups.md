# 12 - Consumers e Consumer Groups

Consumers podem rodar no mesmo hardware ou sistema

Quando falamos que os consumidores estão dentro de um grupo, o Kafka consegue ajeitar para que os consumidores consigam || da leitura de partição

![2662BB7C-6A2D-433D-8D65-96CD44E305B9.jpeg](12%20-%20Consumers%20e%20Consumer%20Groups%20175c1d17f581474e91842feaba51bba5/2662BB7C-6A2D-433D-8D65-96CD44E305B9.jpeg)

![E5C3269D-480D-45A7-BA76-B299F741DE3B.jpeg](12%20-%20Consumers%20e%20Consumer%20Groups%20175c1d17f581474e91842feaba51bba5/E5C3269D-480D-45A7-BA76-B299F741DE3B.jpeg)

Não tem como 2 consumidores, que estão no mesmo grupo, lerem a mesma partição

É sempre assim, em um grupo X, um consumer por partição. 

O que pode acontecer é 2 consumers em grupos diferentes, lerem a mesma partição.

Se tiver mais consumer do que partição, vai ter algum consumer que vai ficar parado sem ler nenhuma partição

Não adianta criar várias partições para poucos consumers, e também não adianta ter vários consumers, se a quantidade de consumers é maior que as partições.

O ideal mesmo, é a mesma quantidade de partições, serem a mesma quantidade de consumers.

Trabalhar com grupos de consumo é muito comum, sempre devemos citar o grupo desses consumidores.

Se não falarmos, o grupo está por padrão, sendo o(s) proprio(s) consumidor(es)