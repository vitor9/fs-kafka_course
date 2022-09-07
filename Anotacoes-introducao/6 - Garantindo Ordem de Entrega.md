# 6 - Garantindo Ordem de Entrega

Com toda a flexibilidade das partições, acaba surgindo um novo problema, que seria o seguinte…

Em um sistema bancário, pode acontecer de um consumer1 que faz o processamento de uma partição que guarda mensagens de transferência, estivesse lento, e o seu outro consumer2, estivesse mais rápido, e por conta disso, processasse a partição2 que segura msgs de estorno mais rápido que o consumer1.

Ou seja, não temos uma ordem para que isso aconteça, se o consumer1 estiver lento, os outros que não estão vão ler as outras mensagens antes que ele consiga acompanhar.

![63EF7A1F-DACF-4DEA-A3D4-42DC28BAAF66.jpeg](6%20-%20Garantindo%20Ordem%20de%20Entrega%200d3b1b3cf15f4a259c6c4b799fdcc1b4/63EF7A1F-DACF-4DEA-A3D4-42DC28BAAF66.jpeg)

Por isso é importante definirmos a ordem de entrega, assim, a partição 1 que o consumidor1 consome, sempre estará processando na devida ordem de transferência, e estorno.

(0 e 1 nas mensagens representam o offset delas)

![77CE1552-43C3-4513-BDC7-1CBD640A8DFD.jpeg](6%20-%20Garantindo%20Ordem%20de%20Entrega%200d3b1b3cf15f4a259c6c4b799fdcc1b4/77CE1552-43C3-4513-BDC7-1CBD640A8DFD.jpeg)

Podemos definir a ordem de entrega dessas msgs com as Keys.

Toda vez que eu mandar uma msg, falamos que a msg da transferência(msg 0), é igual a movimentação. E enquanto a msg de estorno(msg 1), falamos que a key dela é movimentação.

O Kafka vai mandar as msgs com a Key especificada, sempre para uma determinada partição.

![6D9DC004-400D-4BD0-9BB8-5A465EE59BFF.jpeg](6%20-%20Garantindo%20Ordem%20de%20Entrega%200d3b1b3cf15f4a259c6c4b799fdcc1b4/6D9DC004-400D-4BD0-9BB8-5A465EE59BFF.jpeg)

Quando quero garantir a ordem, uso a msm key para as msgs que tem que estar em ordem, porque vão estar na mesma partição.

Quando não preciso ter ordem, não preciso informar nenhuma key, que ele faz isso de forma aleatória com diversos consumidores lendo.

No registro na hora em que é enviado a msg, especificamos a anatomia:

- Header
- Key - movimentação(como dito antes, serve tanto para transf/estorno)
- Mensagem/Value - transferência / estorno

Novamente, o Kafka por conta que consegue escalar, os consumidores conseguem agir mais rápido por conta da distribuição e a responsabilidade deles em ler em cada partição as msgs, e assim varios consumidores leem ao mesmo tempo.