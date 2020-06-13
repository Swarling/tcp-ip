---
layout: default
title: Diseño de Protocolos de Red
nav_order: 11
permalink: /diseno-protocolos-red
---
##### **Autores:** 
{: .no_toc }
[Jimmy Morales](https://github.com/jimmymorales)

##### **Fecha de creación:** 
{: .no_toc }
12-06-2020

##### **Revisiones:**  
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Diseño de Protocolos de Red
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
El objetivo de las redes es lograr comunicar diferentes equipos entre sí, y las computadoras son dispositivos que tienen la capacidad de ejecutar múltiples procesos simultáneamente. ¿Cómo deben los hosts (equipos finales) ponerse de acuerdo para intercambiar mensajes?. Para esto se definen reglas, sintaxis y como se sincronizará la información. En el ámbito de telecomunicaciones estas reglas son definidas por organizaciones internacionales como la [IETF] e [IEEE].

Desde los inicios de lo que conocemos como el Internet, sus creadores fueron pensando en arquitecturas para que los protocolos de comunicación en redes fueran mantenibles, por esto decidieron implementar una arquitectura en capas, donde cada capa posee funciones y protocolos específicos. También se definió el encapsulamiento como una manera de comunicación entre las capas en el stack de TCP/IP.

![Comunicacion optica](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/US_Navy_030611-N-3160B-003_Signalman_Seaman_Adrian_Delaney_practices_his_semaphore.jpg/320px-US_Navy_030611-N-3160B-003_Signalman_Seaman_Adrian_Delaney_practices_his_semaphore.jpg)

## Protocolos
Un protocolo es un conjunto de reglas que determina todos los aspectos de una comunicación. Son convenciones que permite que la comunicación entre dos hosts se de. Los protocolos pueden ser implementados tanto en hardware, software o una comunicación de ambos.

Para que la comunicación sea exitosa, hay varios aspectos que el protocolo tiene que definir:
  * Conexión física. Los hosts generalmente tienen hardware que dependen de diferentes fabricantes. Los protocolos establecen cómo se va a manejar ese diferente equipo para que sea compatible con otro equipo de otro fabricante.
  * Handshaking. El handshaking es una serie de pasos que se realizan al iniciar una comunicación entre dos hosts.
  * Negociación de parámetros.
  * Las fronteras de un mensaje. Definen cuando inicia un mensaje y cuando termina.
  * Formato y estructura del mensaje.
  * Detección de errores. Un protocolo puede definir como saber que un mensaje está corrupto y cómo manejarlo.
  * Puede realizar un tipo de corrección de errores o simplemente descartar el mensaje.
  * Finalización de la comunicación entre dos hosts.


## Estandares y organizaciones
Los estándares promueven una sana competencia entre todos los fabricantes de hardware y software. Un estándar es una especificación de una tecnologia o metodologia aplicable al internet. Al tener un estándar, cualquiera puede generar un hardware que se apegue a ese estándar y pueda ser compatible a toda la estructura de Internet.

El objetivo de Internet es generar un interconexion que pueda extenderse a través de todo el  mundo de una forma que pueda llegar a cubrir gran parte de él. Para esto se crearon varias organizaciones que crean reglas para esto.

### Internet Engineering Task Force (IETF)
Es la organización que regula el suite de protocolos TCP/IP.

### Institute of Electrical and Electronics Engineers (IEEE)
Es una asociación profesional de ingeniería electrónica e ingeniería eléctrica. Es famosa por su desarrollo en el estándar de redes locales WIFI 802.11.

### International Standards Organization (ISO)
Es la organización que se encarga a nivel mundial de mantener los estándares en general. Desarrollo el modelo de referencia OSI.

## Arquitectura en capas
Los protocolos en distintas capas nos permite tener la estructura de Internet que funciona en la actualidad. El proceso de comunicación se divide en capas funcionales. Las redes de comunicación se basan en su totalidad en protocolos organizados en una forma jerárquica de capas. El concepto de esto es que cada capa en el suite de protocolos tiene un objetivo diferente que las demás y muy específico. 
![Arquitectura en capas en la suite TCP/IP](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/IP_stack_connections.svg/525px-IP_stack_connections.svg.png)

Las ventajas de tener un diseño en capas:
  * Es mucho más fácil hacer búsqueda de fallas y errores. Se puede analizar modulo por modulo.
  * Nos permite también tener una forma más fácil de generar nuevas implementaciones.
  * Nos permite la demultiplexion.
  
No solamente el sistema debe ser modular sino también realizar un análisis de qué funciones realizaran las capas.

## Encapsulamiento
Es necesario fragmentar los mensajes para que el medio pueda ser utilizado por diferentes procesos. Para hacer esta de-multiplexión se pasa cada fragmento por encapsulación. Encapsulación es agregar información importante a cada uno de estos fragmentos para que cada capa pueda ejecutar las acciones asignadas. Cada unidad que pertenece a una capa se llama PDU (Protocol Data Unit). Cada capa tiene una unidad de información que está relacionada con ella. 
![Encapsulacion](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/UDP_encapsulation.svg/525px-UDP_encapsulation.svg.png)

[IETF]: https://www.ietf.org/
[IEEE]: https://www.ieee.org/

## Referencias
1. [Internet Protocol Suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)
