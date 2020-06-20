---
layout: default
title: Unicast y Multicast
nav_order: 15
permalink: /unicast-wifi
---
##### **Autores:**
{: .no_toc }
[Santiago Wever](https://github.com/sweverG)

##### **Fecha de creación:** 
{: .no_toc }
19 de junio del 2020

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Unicast y Multicast
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Introducción

En una red funcional todos sabemos que siempre hay paquetes moviéndose entre servidores y pasan por diferentes dispositivos que se encuentran dentro de esa red. En esta sección se explicará algunos de las diferentes métodos que existen para enviar paquetes entre servidores y entre cualquier dispositivo de red.

Los métodos que se explicarán en esta sección son **Unicast** y **Multicast**. Existen otras formas de transmitir paquetes, como [Broadcast](https://es.wikipedia.org/wiki/Difusi%C3%B3n_amplia), que no se verán en esta sección, pero recomiendo investigarlo de igual manera.

![Ejemplos](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fsupport.huawei.com%2Fhuaweiconnect%2Fenterprise%2Fen%2Fdata%2Fattachment%2Fforum%2Fdm%2Fecommunity%2Fuploads%2F2016%2F0331%2F14%2F56fcbe26d525e.png&f=1&nofb=1)



## Unicast

El método **Unicast** es utilizado para una comunicación de red en donde paquetes de información son transmitidos de un punto a otro, es decir que en esta comunicación solo existe un receptor y un emisor. Básicamente los paquetes solo tienen un destino y se podría decir que éste es el método de transmisión de paquetes más utilizado en la red, ya que protocolos que utilizan [TCP](https://es.wikipedia.org/wiki/Protocolo_de_control_de_transmisi%C3%B3n) como [HTTP](https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_hipertexto), [SMTP](https://es.wikipedia.org/wiki/Protocolo_para_transferencia_simple_de_correo), [FTP](https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_archivos) y [TELNET](https://es.wikipedia.org/wiki/Telnet) utilizan el método Unicast para transmitir paquetes de un servidor a otro.

![Unicast](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F7%2F75%2FUnicast.svg%2F1200px-Unicast.svg.png&f=1&nofb=1)



## Multicast

El método Multicast es utilizado para una comunicación de red en donde paquetes de información son transmitidos de un punto a múltiples puntos específicos, es decir que en esta comunicación puede existir uno o más emisores y un grupo de receptores. El grupo de receptores es limitado, es decir que los paquetes no tienen de destino a todo dispositivo que se encuentren, sino que es un grupo de receptores determinado a donde se transmiten los paquetes.

Un ejemplo de la utilización de este método es en un servidor que transmite vídeo en vivo a un grupo de suscriptores. Transmitir vídeo de alta definición a múltiples receptores puede agotar el ancho de banda de la red, lo cual puede generar inestabilidad y al implementar el método Multicast se puede lograr mayor estabilidad en la red al transmitir el vídeo a un grupo grande de receptores.

![Multicast Video](https://ramp.com/wp-content/uploads/2017/04/Web-Diagram-Multicast-1024x545.png)

Este método es una técnica de red en donde envía el mismo paquete simultáneamente a un grupo de receptores y ya que [TCP](https://es.wikipedia.org/wiki/Protocolo_de_control_de_transmisi%C3%B3n) solamente soporta Unicast, Multicast utiliza [UDP](https://es.wikipedia.org/wiki/Protocolo_de_datagramas_de_usuario).

![Multicast](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F3%2F30%2FMulticast.svg%2F1200px-Multicast.svg.png&f=1&nofb=1)