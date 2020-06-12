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
**Esta es una prueba de modificación del documento.** realizado por Anibal Leal.  


## PING
Ques es

## Formato

Solicitud 

![](C:\Users\aleal\AppData\Roaming\Typora\typora-user-images\image-20200611230726370.png)

Respuesta

![image-20200611230932634](C:\Users\aleal\AppData\Roaming\Typora\typora-user-images\image-20200611230932634.png)

## Estructura del paquete

### Windows

Usage: ping [-t] [-a] [-n count] [-l size] [-f] [-i TTL] [-v TOS]
            [-r count] [-s count] [[-j host-list] | [-k host-list]]
            [-w timeout] [-R] [-S srcaddr] [-c compartment] [-p]
            [-4] [-6] target_name

Options:
    -t             Ping the specified host until stopped.
                   To see statistics and continue - type Control-Break;
                   To stop - type Control-C.
    -a             Resolve addresses to hostnames.
    -n count       Number of echo requests to send.
    -l size        Send buffer size.
    -f             Set Don't Fragment flag in packet (IPv4-only).
    -i TTL         Time To Live.
    -v TOS         Type Of Service (IPv4-only. This setting has been deprecated
                   and has no effect on the type of service field in the IP
                   Header).
    -r count       Record route for count hops (IPv4-only).
    -s count       Timestamp for count hops (IPv4-only).
    -j host-list   Loose source route along host-list (IPv4-only).
    -k host-list   Strict source route along host-list (IPv4-only).
    -w timeout     Timeout in milliseconds to wait for each reply.
    -R             Use routing header to test reverse route also (IPv6-only).
                   Per RFC 5095 the use of this routing header has been
                   deprecated. Some systems may drop echo requests if
                   this header is used.
    -S srcaddr     Source address to use.
    -c compartment Routing compartment identifier.
    -p             Ping a Hyper-V Network Virtualization provider address.
    -4             Force using IPv4.
    -6             Force using IPv6.

### Linux

### IOS