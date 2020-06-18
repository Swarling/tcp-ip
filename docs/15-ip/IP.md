---
layout: default
title: IP
nav_order: 25
permalink: /ip
---
##### **Autores:** 
{: .no_toc }
[Diego Arias](https://github.com/diegoarias2t)

##### **Fecha de creación:** 
{: .no_toc }

##### **Revisiones:**  
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# IP
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---

## IP
IP trabaja bajo el concepto de "Best Effort". No es un protocolo orientado a conexión debido a que no mantiene ninguna información con respecto al estado.

- Los datagramas no llegan siempre en el orden que son enviados.
- Los datagramas se pueden corromper en el camino.
- IP deja que estas tareas sean resueltas por capas superiores.

## Entrega del mejor esfuerzo
En un sistema diseñado bajo la "entrega del mejor esfuerzo" todos los hosts reciben la mejor calidad de servicio posible, sin embargo, esto no garantiza que los datos lleguen al destino requeridos.

## No orientado a conexión
IP al igual que UDP son protocolos no orientados a conexión (a diferencia de TCP), y básicamente se refiere a que se podrá establecer una comunicación entre dos usuarios de la red, sin haber realizado una conexión o sincronización previa.

## Header
Posee un tamaño variable, con una medida máxima 60 bytes, pero usualmente son 20 bytes.

## Direcciones
Cuando hablamos de dirección IP nos referimos a un identificador de hosts perteneciente a la capa 3 del modelo OSI. Actualmente podemos encontrar dos tipos de direcciones IP
- IPV4
- IPV6

Las direcciones IPV4 están compuestas por cuatro octetos de ocho bits cada uno, es decir estamos hablando de una dirección total de 32 bits. Estas son las más utilizadas actualmente en el ámbito de las telecomunicaciones en general.

## Big endian vs Little Endian

- Big Endian = bits más significativos a la izquierda y menos significativos a la derecha. La ventaja de este tipo es que es más fácil leer.
- Little Endian = bits más significativos a la derecha y menos significativos a la izquierda. La ventaja de este tipo es que es utilizado en nuevos procesadores utilizan esta notación.

## DFS (Differentiated Services Field) 
El campo de servicios diferenciados (DFS) es un método que nos ofrece IP, el cual tiene como propósito garantizar la calidad de servicio en redes muy complejas. Esto lo realiza por medio de la clasificación de cada paquete IP según los parámetros QOS que sean requeridos dependiendo de la red.

## ECN (Explicit Congestion Notification)
ECN como su nombre lo indica, es una notificación que forma parte del protocolo IP, la cual es utilizada para anunciar congestión o saturación en la red y evitar así perdida de paquetes.

## Total Length
Es una sección de 16 bits en el datagrama IP, la cual nos indica la longitud total del paquete IP.

## Fragmentación
Es una caracteristica que permite dividir un paquete en varios paquetes más pequeños, esto sucede cuando el paquete supera el MTU. Cabe resaltar que se puede activar una flag (DF) para restringir la fragmentación de los paquetes. 

## Time To Live
El TTL es una sección que forma parte del header IP y tiene un tamaño de 8 bits. Esta sección nos indica cuantos saltos puede dar un paquete antes de ser descartado. Un claro ejemplo del funcionamiento de esto se puede apreciar mediante la herramienta traceroute. Por lo general es un valor de 32 o 64 saltos.

## Protocolo
Nos indica el número de protocolo que se está utilizando en dicho paquete IP.
- 6 = TCP
- 17 = UDP

## Internet Checksum
Es un algoritmo utilizado para la detección de errores en los paquetes que se reciben. Esto es realizado básicamente para incrementar la confiabilidad de la red. Este algoritmo se basa en la suma de todos los caracteres de 16 bits que conforman el mensaje y el resultado es transmitido junto con el mensaje, del otro lado, el receptor realiza la misma suma y compara los checksum, si estos son iguales, el mensaje ha sido enviado correctamente.

## Unicast, Broadcast, Multicast
-Unicast: Envío a un único host destino.
-Multicast: Envío a todos los hosts suscritos a un grupo.
-Broadcast: Envío a todos los hosts que formen parte del mismo segmento de red en el que se encuentre el emisor.

## Ruteo IP
Es el proceso el cual nos permite interconectar diferentes segmentos de red, esto se realiza mediante "enrutamiento" lo cual nos permite encontrar el mejor camino entre todos los posibles para llegar a una red destino. Este proceso puede ser estático o dinámico.

## Tabla de enrutamiento IP
Es la tabla que almacena todas las rutas que forman parte de nuestra red. Cuando necesitamos llegar a una red destino, en la tabla de enrutamiento encontramos cual es nuestro siguiente salto para llegar a dicha red.

## Entrega Directa
Una entrega directa se refiere a que el emisor y el receptor se encuentran en el mismo dominio de broadcast. En este caso los campos de SRC MAC y SRC IP contienen el mismo host (emisor) y los campos DST MAC y DST IP contienen al receptor, a diferencia de una entrega indirecta.

## Entrega Indirecta
Una entrega indirecta hace referencia a cuando el mensaje debe atravesar más de un router para llegar a su destino. Esto quiere decir que el receptor no se encuentra en el mismo dominio de broadcast.

## Preguntas

### Pregunta 1
¿Qué utilidad tiene el TTL en la herramienta traceroute?

### Pregunta 2
Si existen dos rutas para llegar al mismo destino ¿En que se basa la decisión para elegir cuál de las dos tomar?