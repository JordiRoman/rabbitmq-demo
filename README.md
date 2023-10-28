# Rabbitmq

Servidor de mensajeria para programacion

## Bibliografia

* https://www.netmentor.es/entrada/rabbitmq-comunicacion-asincrona

## Configuracion

Es posible configurarlo directamente desde :
* ficheros de configuracion (antes de arrancar el servicio)
* linea de comandos (con el servicio arrancado)
* desde un dashboard ( con el servicio arrancado )

## Ideas/definiciones

Cola
: Lo que todos pensamos, una tuberia en la que *1 productor* envia mensajes a *1 consumidor* FIFO.
: Si no hay consumidor, el mensaje se almacena esperando que alguien lo reciba.

Exchange
: Es parecido a una cola pero permite a *1 productor* enviar mensajes a *VARIOS consumidores*
: Los _exchanges_ no almacenan mensajes de forma que todo lo que entra sale, pero ademas ningun consumidor se puede subscribir directamente a un _exchange_
: Asi pues debemos hacer un *binding* de un exchange a 1 o varias colas (o a otros exchanges).
: Hay exchanges predefinidos en los VHOSTS

Broker
: Será el conjunto de colas, exchanges y bindings

Routing-key
: Es un identificador de los mensajes que admite la cola
: Se admiten comodines, el '*' substituiria a una palabra. El '#' indica que la palabra es opcional.
: demo.* equivale a 'demo.algo' pero no a 'demo'
: demo.# equivale a 'demo' y a 'demo.demo2'


vhost
: Es un elemento logico que nos permite crear agrupaciones de colas.
: Dado que en un servidor no puede haber 2 colas con el mismo nombre, para estructuras repetitivas nos va perfecto
: Por ejemplo, podriamos tener el vhost guaca-sbd con las colas wol, reservas, etc


## Tipos de exchanges

* direct
* routing-key
* header 
* fanout
* ...

### direct



