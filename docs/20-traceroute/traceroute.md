---
layout: default
title: Traceroute
nav_order: 30
permalink: /traceroute
---
##### **Autores:**
{: .no_toc }
[Diego Alay](https://github.com/diegoalay)

##### **Fecha de creación:** 
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# TÍTULO
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
Traceroute permite determinar la ruta que tomarán los datagramas desde un host a otro y mide el tiempo en el tránsito de dicha ruta a travéz de una red IP. Hace uso del protocolo ICMP y del campo TTL el cual va incrementando por cada mensaje ICMP enviado. 

Al utilizar traceroute envía datagramas UDP por default pero también puede ser configurado para enviar mensajes ICMP utilizando TCP. 

## Time To Live
El TTL es una campo que esta ubicado en el encabezado IP y tiene un tamaño de 8 bits. TTL nos indica cuantos saltos puede dar un paquete antes de ser descartado.s

## Funcionamiento
Traceroute funciona enviando un paquete a un puerto UDP abierto en una máquina destino. En un inicio
traceroute envía un datagrama IP con TTL de valor igual a 1. El primer router recibe el datagrama con un TTL igual a 1 este decrementa el TTL a 0 y devuelme un mensaje ICMP indicando que el TTL expiró esto indica cuál fue el primer salto y cuánto tardó el proceso de llegar hasta dicho router.Traceroute repite el proceso enviando ahora un datagrama con TTL igual a 2 el cual logra hasta el segundo router este al decrementar el TTL a 0 devulve nuevamente un mensaje ICMP de TTL expidado y así sucesivamente hasta que el paquete alcanza el destino deseado o realice un total de 30 saltos tomando en cuenta que no se modifico y se dejo el valor default.

Los tiempos de respuesta puede verse alterados en gran manera por varias razones:
* Paquete cruza largas distancias. 
* Congestión de red

## Tracert vs Traceroute
Depende del sistema operativo que se este utilizando por ejemplo para sistemas operativos basados en unix se hace uso de traceroute y tracert en Windows. El comando traceroute envía paquetes UDP a diferencia de Windows el cual envía peticiones de eco ICMP. 

### Pregunta 1
¿ Qué diferencia es revelante entre traceroute y tracert?

### Pregunta 2
¿ Cúal es el TTL por default de traceroute ?

## Referencias

[1] Haulmer, “Guía Básica de la Herramienta Traceroute”, 2019. [Online]. Available: https://www.statista.com/statistics/617136/digital-populationworldwide/.

[2] Wix, “Definición de TTL”, 2006. [Online]. Available: https://support.wix.com/es/article/definici%C3%B3n-de-ttl. 

[3] Statista, “How does traceroute work?”, 2018. [Online]. Available: https://www.perl.com/article/how-does-traceroute-work-/.

[4] enmimaquinafunciona, “Diferencia entre Tracert y Traceroute” The Statistics Portal, 2016. [Online]. Available: https://www.enmimaquinafunciona.com/pregunta/67482/diferencia-entre-tracert-y-traceroute.



