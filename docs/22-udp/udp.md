---
layout: default
title: UDP
nav_order: 32
permalink: /udp
---
##### **Autores:** Marvin Chigüil 
{: .no_toc }


##### **Fecha de creación:** 08/06/2020 
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# UDP (User Datagram Protocol)
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
La comunicación entre dispositivos se basa en protocolos de internet. IP es el más conocido pues ahí se encarga del direccionamiento y la fragmentación de los datagramas, la transmisión de datos usualmente se lleva a través de TCP pues es un protocolo orientado a la conexión por lo que es fiable, a pesar de esto la transmisión es un poco lenta, UDP es un protocolo que su idea principal es ser rápido pero no confiable.


## Definición
UDP es un protocolo que permite la transmisión sin conexión de datagramas, pertenece a la familia de protocolos de internet, se encuentra entre la capa de red y la capa de aplicación. Es una alternativa a TCP para mantener el tiempo de transmisión lo más bajo posible. Un usuario puede enviar información muy rápido sin esperar que el destino responda, no hay garantía de que este mensaje llegue a diferencia de TCP, tampoco es seguro, sin embargo tiene un Checksum que lo utiliza para detectar datagramas que llegaron mal.

### Características

UDP envía datagramas incluso cuando no se haya establecido conexión entre el emisor y el receptor. El datagrama se envía a la dirección IP especificando el puerto.

Al igual que TCP, UDP utiliza puertos para permitir que los datagramas se transfieran a los protocolos correctos. Los puertos reservados están entre el 0 y 1023.

UDP permite una comunicación rápida y sin retardo, está orientado a lo que es el streaming de datos, muchas veces van a perderse datagramas pero es parte de que no nos garantice que le lleguen al receptor.

No ofrece garantía de seguridad, no ofrece que los datagramas lleguen completos o que lleguen en el orden que deberían, por eso los servicios son los que deben encargarse de revisar esto.

## Datagrama UDP

El datagrama UDP consiste en cuatro segmentos más la data, los cuatro campos son de 2 bytes cada uno. La "Data" va seguido del header y este es el payload. En IPv4 el checksum y el source son opcionales, en IPv6 solo el surce es opcional.

![A Brief Notes On UDP And TCP Protocols In Computer Networks](https://www.tutorialsweb.com/networking/tcp-ip/images/fig8_UDP.jpg)

El source identifica el puerto del que lo envía, si no se utiliza este será cero. Destination indica el puerto de quien recibe el datagrama. El length especifica el tamaño en bytes del header, el tamaño mínimo es de 8 bytes. el checksum se utiliza para determinar si hubo algún error en el envío, pero no corrige este error.

