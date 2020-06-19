---
layout: default
title: Red Compartida
nav_order: 14
permalink: /red-compartida
---
##### **Autores:** 
{: .no_toc }
[Diego Alay](https://github.com/diegoalay)
[Jaime Ramirez](https://github.com/jjjramirez)

##### **Fecha de creación:** 
{: .no_toc }

##### **Revisiones:**  
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Red Compartida
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Store and Forward Networks
En las redes Store and Forward cada dispositivo a través de la red, un switch o un router, tiene la función de almacenar un mensaje completo antes de hacer forward, el mensaje es almacenado en los buffers del dispositivo. 

Antes de que existieran las redes Packet Switching esto era un gran problema, si un dispositivo enviaba un mensaje muy grande y ocurre un error todo el mensaje se pierde, también si es muy grande el mensaje se pueden llenar los buffers de un router por lo que los mensajes de otros dispositivos se van a perder.

El método de store and forward es utilizado en redes packet switching en la que cada router almacena los paquetes que recibe antes de enviarlos para realizar el proceso de ruteo. Esto también hace que los routers tengan que almacenar todos los paquetes que reciben en buffers y si ya no tienen espacio se van a perder los paquetes.

Aunque este problema parezca grave es la única forma para que los routers puedan realizar los algoritmos de ruteo. Si no almacenará el paquete y solo lo reenviará no podría leer los campo que este lleva en el header para saber hacia dónde enviarlo y ningún algoritmo de ruteo funcionaria.

## Research Networks
Las redes más simples con las que iniciaron en redes donde solo existían dos computadoras conectadas directamente entre ellas. Pero aquí surge un problema si se quería que una computadora estuviera conectada con otras, primero no todas están cerca geográficamente, y no es factible tener un cable que atraviese varios kilómetros solo para conectar dos computadoras, y también se necesita un cable por cada computadora.

Entonces se preguntaron,  ¿Cómo hacer para no tener que conectar dos computadoras directamente?

¿Cómo hacerlo de manera eficiente?

¿Como hacer para que las caídas en los enlaces no fueran un problema ?

A partir del año 1960 en Estados Unidos empezaron a buscar un solución para estos problemas y antes del 1970 se creó el inicio de lo que fue conocido como ARPANET (Advanced Research Projects Agency Network) con el objetivo de conectar dispositivos en todo Estados Unidos.

Con ARPANET se empezó a usar la técnica de packet switching junto con store and forward, se creó el core de la red conformado por routers los cuales tenían como única finalidad controlar el tráfico en la red (Principio End to End).

Junto con ARPANET se empezaron a desarrollar los protocolos y el modelo de capas que ahora es conocido como TCP/IP.

Para el año 1977 en la red ya estaban conectados redes internas de organizaciones del gobierno de Estados Unidos y Universidades a través de todo el país. Luego de varios años de investigación ARPANET termino y con las bases creadas surgió Internet.

![ARPANET EN 1977](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Arpanet_logical_map%2C_march_1977.png/800px-Arpanet_logical_map%2C_march_1977.png)

## Packet Switching
La técnica de Packet Switching consiste en dividir un mensaje grande en mensajes más pequeños que son encapsulados y son llamados paquetes. Cada paquete tiene que tener un receptor y un emisor y en algunos protocolos se puede agregar un número de secuencia para volver a ordenarlo.

Los paquetes pueden pasar por distintos caminos en la red esto garantiza que la red pueda funcionar aunque algún enlace deje de funcionar, pueden llegar en diferente orden al que fueron enviados, si un paquete se pierde ya no es un problema tan grave ya que se puede volver a retransmitir solo el paquete perdido en lugar de todo el mensaje.

## Red Compartida, Principio Extremo a Extremo
ARPANET fue la primera red compartida en la que las redes de diferentes universidades o de diferentes organizaciones del gobierno podían estar conectadas entre ellas para poder compartir información. La forma en la que se crearon las redes compartidas consiste en una serie de saltos (routers) que tienen funciones simples y básicas para retransmitir paquetes y que lleguen a su destino mientras que los host que envían y reciben paquetes se encargan del procesamiento (End to End). Esta es la infraestructura de red compartida.

De manera sencilla el principio end-to-end consiste en tener equipo de routing sencillo los cuales no hacen mayor procesamiento, se puede decir que son transparentes y no intervienen en la comunicación por lo cual todo el procesamiento pesado se hace en los dispositivos que están en los extremos dado que son dispositivos inteligentes. Los dispositivos intermedios solo se encarga de realizar procesos de ruteo para que los paquetes puedan llegar a su destino, no importa si estan en orden o si está fragmentado, o si el mensaje que va dentro del paquete tiene errores. Los dispositivos finales si se pueden encargar de todas estas funciones.