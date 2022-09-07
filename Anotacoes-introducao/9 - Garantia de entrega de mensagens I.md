# 9 - Garantia de entrega de mensagens I

Como podemos garantir que a nossa mensagem foi entregue?

## Producer: Garantia de Entrega

Na hora que o producer enviar uma msg, ele vai poder settar parametros. Um deles, é o Ack, que é acknowledgement.

Tipos de Garantia de entrega

**Ack 0 - None**, informamos que toda vez que é enviado uma msg, nao precisa retornar falando que a msg chegou ou gravou. Também chamado de FF(Fire and Forget).

Isso é bom e ruim, por um lado ruim, não temos a confirmação do que houve com a msg, porém, temos mais desempenho e mais envios de mensagens porque não precisa ficar avisando o que ocorre com essas msgs. Podemos perder mensagens dessa forma.

![52646C98-16FA-4085-B1DC-D8269C862C7B.jpeg](9%20-%20Garantia%20de%20entrega%20de%20mensagens%20I%200e5dfccb9f5649d2984fe6057a16c78e/52646C98-16FA-4085-B1DC-D8269C862C7B.jpeg)

**Ack 1 - Leader**, 

O Producer manda a msg, ela bate no lider e o lider salva a msg, depois ele manda a msg para o Producer falando que salvou a msg. 

Se o broker do líder ficar fora, não vai ter tempo dele replicar a msg para os followers. Então isso gera perda de msg, e o producer acredita que a msg é guardada, quando na verdade não foi.

Afeta a performance mas temos a garantia de entrega

![1F15AE36-EEF6-4F23-8873-99DE735D3552.jpeg](9%20-%20Garantia%20de%20entrega%20de%20mensagens%20I%200e5dfccb9f5649d2984fe6057a16c78e/1F15AE36-EEF6-4F23-8873-99DE735D3552.jpeg)

Ack -1 - ALL

Utilizado quando não pode perder de maneira alguma a msg.

O producer produz a msg, vai bater no lider, ele salva e ai o lider vai replicar as msg nos fllowers. Os Followers avisam ao lider que as msgs foram salvas e ai sim, o líder avisa ao producer que a msg foi salva.

É a maneira que mais afeta a performance mas com 100% de garantia.

Além de o lider ter que salvar e voltar a avisar ao producer, ele tem que salvar, replicar, aguardar a resposta dos followers que foi replicado, ai ele consegue avisar ao producer que foi gravado.

![A347802A-9F44-45D2-9321-C3AF5726DBE9.jpeg](9%20-%20Garantia%20de%20entrega%20de%20mensagens%20I%200e5dfccb9f5649d2984fe6057a16c78e/A347802A-9F44-45D2-9321-C3AF5726DBE9.jpeg)