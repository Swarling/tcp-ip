---
layout: default
title: ICMP
nav_order: 28
permalink: /icmp
---
##### **Autores:**
{: .no_toc }

Carlos Cetino


##### **Fecha de creación:** 
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# TÍTULO
{: .no_toc }

ICMP



#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


# Resumen
El protocolo ICMP solamente informa de incidencias en la entrega de paquetes o de errores en la red en general, pero no toma decisión alguna al respecto. Esto es tarea de las capas superiores.

# ICMP

ICMP es un protocolo de nivel de transporte dentro de TCP / IP que comunica información sobre problemas de conectividad de red a la fuente de la transmisión comprometida. Envía mensajes de control tales como la red de destino inalcanzable, la ruta de origen falló y el apagado de origen. Utiliza una estructura de paquete de datos con un encabezado de 8 bytes y una sección de datos de tamaño variable.

## **¿Cómo funciona ICMP?**

ICMP es utilizado por un dispositivo, como un enrutador, para comunicarse con la fuente de un paquete de datos sobre problemas de transmisión. Por ejemplo, si no se entrega un datagrama, ICMP podría informarlo al host con detalles para ayudar a discernir dónde salió mal la transmisión. Es un protocolo que cree en la comunicación directa en el lugar de trabajo.

Cabecera del Internet Control Message Protocol

![Encabezado ICMP](https://www.ionos.es/digitalguide/fileadmin/DigitalGuide/Screenshots/ES-ICMP-1.PNG)

 

ICMP es parte del conjunto de protocolos IP tal cual y como se definió en la RFC 792. Los mensajes ICMP son comúnmente generados en respuesta a errores en los Datagramas de IP o para diagnóstico y ruteo. La versión de ICMP para IPv4 también es conocida como ICMPv4. IPv6 tiene su protocolo equivalente ICMPv6. Los mensajes ICMP son construidos en el nivel de capa de red. IP encapsula el mensaje ICMP apropiado con una nueva cabecera IP (para obtener los mensajes de respuesta desde el host original que envía), y transmite el datagrama resultante de manera habitual.

La utilidad del protocolo ICMP es controlar si un paquete no puede alcanzar su destino, si su vida ha expirado, etc. Es decir, se usa para manejar mensajes de error y de control necesarios para los sistemas de la red, informando con ellos a la fuente original para que evite o corrija el problema detectado.

Muchas de las utilidades de red comunes están basadas en los mensajes ICMP. El comando traceroute está implementado transmitiendo datagramas UDP con campos especiales TTL IP en la cabecera, y buscando los mensajes de "Tiempo de Vida en tránsito" y "Destino inalcanzable" generados como respuesta. La herramienta ping está implementada utilizando los mensajes "Echo request" y "Echo reply" de ICMP.

 

Lista de mensajes de control permitidos (incompleta):

0 - Echo Reply

1 - Reservado

2 - Reservado

3 - Destination Unreachable

4 - Source Quench

5 - Redirect Message

6 - Dirección Alterna de Host

7 - Reservado

8 - Echo Request

9 - Anuncio de Router

10 - Solicitud de Router

11 - Tiempo Excedido

12 - Problema de Parámetro

13 - Marca de tiempo

14 - Respuesta de Marca de tiempo

15 - Petición de Información

16 - Respuesta de Información

17 - Petición de Máscara de Dirección

18 - Respuesta de Máscara de Dirección

19 - Reservado para seguridad

20-29 - Reservado para experimentos de robustez

30 - Traceroute

31 - Error de Conversión de Datagrama

32 - Redirección de Host Móvil

33 - IPv6

34 - IPv6

35 - Petición de Registro de Móvil

36 - Respuesta de registro de Móvil

37 - Petición de Nombre de Dominio

38 - Respuesta de Nombre de Dominio

39 - SKIP Protocolo de Algoritmo de Descubrimiento

40 - Photuris, Fallas de Seguridad

41-255 – Reservado

**Conceptos de los mensajes más comunes** 

**0 - Echo Reply**

Echo es simplemente lo que los ingenieros de redes llamamos ' ping '. La respuesta de eco es, como la mayoría supondría, la ' respuesta de ping '. Los ecos ICMP se utilizan principalmente para la resolución de problemas. Cuando hay 2 hosts que tienen problemas de comunicación, algunas solicitudes de eco ICMP simples mostrarán si los 2 hosts tienen sus pilas TCP / IP configuradas correctamente y si hay algún problema con las rutas que toman los paquetes para llegar al otro lado.

**3 - Destination Unreachable**

Es un tipo de paquete ICMP cuya función es transportar un mensaje que es generado por un enrutador, y se envía al host de origen, que recibe el mensaje emitido por el enrutador. El mensaje en sí significa que este router considera inalcanzable el destino al que quiere llegar el host.

**4 - Source Quench**

Usando el Protocolo de mensajes de control de Internet ( ICMP ), un apagado de origen es un mensaje de una computadora host a otra que le dice que reduzca el ritmo al que está enviando paquetes a ese host. El apagado de origen es una de varias formas de administrar el flujo de paquetes en Internet.

**5 - Redirect Message**

Un redireccionamiento ICMP es un mensaje de error enviado por un enrutador al remitente de un paquete IP. Los redireccionamientos se usan cuando un enrutador cree que un paquete se está enrutando de manera subóptima y le gustaría informar al host emisor que debe reenviar los siguientes paquetes a ese mismo destino a través de una puerta de enlace diferente. En teoría, un host con múltiples puertas de enlace podría tener una ruta predeterminada y aprender rutas específicas óptimas a lo largo del tiempo a través de redireccionamientos ICMP

**8 - Echo Request**

(Petición eco) es un mensaje de control que se envía a un host con la expectativa de recibir de él un Echo Reply (Respuesta eco). Esto es conocido como Ping y es una utilidad del protocolo ICMP, subprotocolo de IP. Todo host debe responder a un Echo Request con un Echo Reply que contenga exactamente los mismos datos que el primero