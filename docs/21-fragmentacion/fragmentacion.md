---
layout: default
title: Fragmentación
nav_order: 31
permalink: /fragmentacion
---
##### **Autores:**
Christian Tellez

##### **Fecha de creación:** 
17/6/2020

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Fragmentación

#### Contenido:

Fragmentación IP es un mecanismo que permite separar o "fragmentar" los paquetes IP en múltiples bloques (también llamados fragmentos) dependiendo de si el tamaño del fragmento es mayor al MTU (Maximun Transfer Unit - Unidad Máxima de Transferencia) máximo soportado por los dispositivos. Cuando un datagrama no se puede enviar por un enlace (debido a su tamaño), este datagrama se divide en varios fragmentos.

La fragmentación se puede dar desde el host de salida o puede ser fragmentado por los routers intermediarios. Es importante mencionar que el host final es el único encargado de reconstruir los datagramas fragmentados. 

## ¿Qué es el MTU?
El MTU define el tamaño máximo de los paquetes que una interfaz puede transmitir sin tener que fragmentar el paquete. Mientras más grande sea el MTU, mayor cantidad de bytes pueden ser transferidos en un solo paquete. El valor del MTU tiende a cambiar dependiendo del medio que se esté utilizando; los más utilizados son Ethernet con un MTU de 1500 bytes y WiFi con un MTU de 2312 bytes. 

## Fragmentación en el Header IP

Utilizando como ejemplo el MTU de Ethernet (1500), el header IP tiene por lo general un tamaño de 20 bytes y el resto le pertenece al payload. Cuando la fragmentación se da se ven afectados ciertos campos que veremos a continuación:

![img](https://www.gatevidyalay.com/wp-content/uploads/2018/09/IPv4-Header-1.png) 

1) Identification: Este campo sirve para darles una identificación única a un paquete que fue fragmentado. En la red se van a fragmentar muchos paquetes diferentes pero con esta identificación se podrá saber cómo agruparlos.
2) Don´t Fragment (DM): Este campo indica al router si el paquete se puede fragmentar (valor 0) o no (valor 1). Si por alguna razón, el campo estuviere marcado como 1 (no fragmentar) y el tamaño del frame fuera mayor al MTU de la interfaz del router, el paquete no podría ser fragmentado y al host regresaría un mensaje de error. 
3) More Fragments (MF): Este campo indica si el paquete que está siendo enviado contiene más fragmentos para ser completado. Si el paquete fue fragmentado, el valor será 1 y si el paquete está completo, el valor será 0.
4) Fragment Offset: En caso el frame haya sido fragmentado, este campo indica el orden en el cuál el paquete debe de ser reconstruido. 

## Ejemplo de Fragmentación:

Ahora que ya conocemos los conceptos básicos, veamos algunos ejemplos de cómo la fragmentación ocurre:

- Medio a utilizar: Ethernet
- Tamaño del Frame: 3000 bytes
- MTU: 1500 bytes

Conocemos que el MTU máximo son 1500 bytes y el paquete a transferir pesa 3000 bytes. Para poder transferir este paquete se deberá fragmentar en 3 paquetes con la siguiente distribución:

1er Paquete: Bytes Transferidos 1480
- 20 bytes del Header IP
- 1480 bytes de Payload

2do Paquete: Bytes Transferidos 2960
- 20 bytes del Header IP
- 1480 bytes de Payload

3er Paquete: Bytes Transferidos 3000
- 20 bytes del Header IP
- 40 bytes de Payload
