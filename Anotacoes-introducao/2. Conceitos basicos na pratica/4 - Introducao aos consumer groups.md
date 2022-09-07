# 4 - Introducao aos consumer groups

Relembrando a informação da introdução

> Quando eu digo que 2 consumers fazem parte do mesmo grupo, cada 1 ira ler de uma particao diferente.
> 

Add consumidores a um grupo com o parametro “—group”, que ficara dessa maneira

```bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --from-beginning --group=x
```

O consumidor sera add no nosso grupo “x”.

Ao add nossos 2 consumers no mesmo gp, notamos que as mensagens nao aparecem ao mesmo tempo nos 2 consumidores.

Como eles estão lendo de particoes diferentes, a mesma msg nao chega para os 2 consumidores

Msg para o producer

> >teste 1
>teste 2
>teste 3
> 

output Consumidor 1

> > teste 1
> teste 3
> 

output consumidor 2

> > teste 2
> 

Muito provavel que o consumidor 1 está lendo 2 particoes, e o c2, só 1

Nao interessa quantos consumers temos, quando cada um esta lendo uma particao diferente, nao temos o risco de os nossos consumidores lerem a mesma msg, pq cada consumer fica responsavel por 1 particao diferente