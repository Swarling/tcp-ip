---
layout: default
title: Ping
nav_order: 29
permalink: /ping
---
##### **Autores:**  Anibal Leal
{: .no_toc }


##### **Fecha de creación:**  11-06-2020
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# PING
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
PING es un herramienta de diagnostico muy popular y  sencilla que esta incluida  prácticamente en todos los sistemas operativos y en las aplicaciones que se usan para la administración de redes.  Se utiliza frecuentemente para saber si un host esta activo o para determinar el tiempo (latencia) que se tarda un paquete en llegar de un host a otro.

Dependiendo del sistema operativo que se use, tienen algunas variaciones en los parámetros que se le pueden adicionar a la herramienta.

> Latencia: es el tiempo que se tarde en llegar un paquete de un host a otro.



## Como funciona 

El PING para su funcionamiento utiliza mensajes ICMP,  el host origen envía un mensaje ICMP ECHO REQUEST y el receptor responde con un mensaje ICMP ECHO REPLY.

Cuando se envía el PING, el host origen encapsula dentro del paquete IP el mensaje ICMP que contiene:

- Tipo de mensaje (con valor 8)
- Código de mensaje (con valor 0)
- Checksum 
- Identificador
- Numero se secuencia
- Datos (opcional)

El host destino envía la respuesta con un paquete IP que contiene:

- Tipo de mensaje (con valor 0)
- Código de mensaje (con valor 0)
- Checksum 
- Identificador
- Numero se secuencia
- Datos (opcional)

El identificador y el número de secuencia de la respuesta (ECHO REPLY) deben de ser iguales a los que envió el host que originó la solicitud (ECHO REQUEST).

## Formato mensajes ICMP

### Echo Request

![](C:\Users\aleal\Pictures\Echo Request.png)

### Echo Replay

![](C:\Users\aleal\Pictures\Echo Replay.png)



## Como se usa

Su uso es muy sencillo,  se inicia una sesión de línea de comando en el sistema operativo (ejemplo: En Windows se escribe el comando CMD en el buscador)   y se teclea: 

**ping \<IP o nombre del host\>**



## Sintaxis: 

- [ ] [Microsoft Windows](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/ping)
- [ ] [Ubuntu Linux](http://manpages.ubuntu.com/manpages/trusty/man8/ping.8.html )

