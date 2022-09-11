# 1 - Preparando ambiente para implementação

É essencial entendermos os detalhes do Kafka, ou seja, os conceitos que vimos nas aulas anteriores, como garantia de entrega, grupos de consumidores, etc.

No Dockerfile, sera instalado a seguinte lib

> librdkafka-dev
> 

Ela que faz toda a diferenca para que possamos fazer a comunicação com o Kafka de forma geral. Vamos notar melhor ao subir os sistemas

Essa lib foi feita em C/C++

Ele tem vários language bindings

Ao observarmos o docker-compose, notamos que há um parametro em services, chamado de extra_hosts. Ela basicamente faz com que cocnseeguimos nos comunicar com qualquer container que esteja na rede docker, desde que ele esteja com “extra_hosts”. 

Isso nos poupa ter que ficar criando várias networks.

Toda vez que for acessado o endereço do ”host.docker.internal”, ele irá bater no endereço da nossa máquina (que encontramos no linux em /etc/hosts).

Por padrão, o Docker cria a rede com o docker-compose.

O extra-hosts serve para permitir que outra app de docker-compose também utilize o Kafka.