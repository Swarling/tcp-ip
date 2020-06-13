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

![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/US_Navy_030611-N-3160B-003_Signalman_Seaman_Adrian_Delaney_practices_his_semaphore.jpg/320px-US_Navy_030611-N-3160B-003_Signalman_Seaman_Adrian_Delaney_practices_his_semaphore.jpg)

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
Internet Engineering Task Force (IETF):es el primer organismo de normas de Internet que desarrolla estándares  abiertos a través de procesos abiertos para hacer que Internet funcione  mejor

Institute of Electrical and Electronics Engineers(IEEE): es una asociación mundial de ingenieros dedicada a la normalización y el desarrollo en áreas técnicas

International Standards Organization (ISO): es una organización para la creación de estándares internacionales compuesta por diversas organizaciones nacionales de normalización.



## Arquitectura en capas
Es un diseño de una arquitectura de tipo cliente-servidor que se encuentra separada por capas, las cuales tienen definido sus funciones y la manera de que se comunicaran entre ellas.

La capa de presentación es la que muestra resultados, recibidos por medio de la capa de negocio, al usuario de una manera gráfica y/o entendible.

La capa de negocio es donde se ejecuta todas las "transacciones", como mostrar resultados a la capa de presentación y mandar a guardar datos a la capa de datos.

La capa de datos es en donde se encuentran todos los datos guardados y la capa de negocios le solicita accesar y/o guardar un dato.

La ventaja de este diseño es que se pueden detectar errores en algún módulo específico e implementar nuevos cambios al diseño no afecta todas las capas.

## Encapsulamiento
Create model object and add values to it and `save()` the model. After saving model **model id** and 
**model key** is attached with model object.


## Preguntas

### Pregunta 1
Create model object and add values to it and `save()` the model. After saving model **model id** and 
**model key** is attached with model object.

### Pregunta 2
Create model object and add values to it and `save()` the model. After saving model **model id** and 
**model key** is attached with model object.

[IETF]: https://www.ietf.org/
[IEEE]: https://www.ieee.org/
