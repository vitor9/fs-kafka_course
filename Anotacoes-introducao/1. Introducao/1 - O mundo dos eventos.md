# 1 - O mundo dos eventos

### O que é o Apache Kafka?

> O Apache Kafka é uma plataforma distribuída de streaming de eventos open-source que é utilizada por milhares de empresas para uma alta performance em pipeline de dados, stream de analytics, integração de dados e aplicações de missão crítica.
> 

[https://kafka.apache.org](https://kafka.apache.org/)

### Streaming

Qualquer coisa que produz de forma geral, dados que estão vindo.

Uma vez que conseguimos capturar esses dados, conseguimos distribui-los.

### O mundo dos eventos

Varios sistemas geram eventos, como devices IOT, monitoramento de apps, sistemas de alarmes, gravar histórico, etc. Precisamos utilizarmos os dados da melhor forma possível.

Perguntas:

- Onde salvar esses eventos?
- Como recuperar de forma rápida e simples de forma que o feedback entre um processo e outro, ou mesmo entre um sistema e outro, possa acontecer de forma fluida e em tempo real?
- Como escalo esse processo?
- Como ter resiliência e alta disponibilidade?

A questão é que, **o Kafka é a resposta para todas essas perguntas**.