---
layout: default
title: Path MTU
nav_order: 33
permalink: /path-mtu
---
##### **Autores:**
Christian Tellez


##### **Fecha de creación:** 
Junio 6, 2020

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# TÍTULO
Path MTU Discovery

#### Contenido:
Antes de empezar a definir qué es el Path MTU Discovery, es necesario preguntarnos, qué es el MTU?. El MTU, por sus siglas en ingles, Maximum Transfer Unit o la unidad máxima de transferencia se refiere al tamaño MÁXIMO de los paquetes que se envian a internet. En otras palabras, es el limitante que indica de qué tamaño máximo debe de ser el paquete para ser transmitido por la capa de enlace de datos.

En Ethernet, el MTU máximo que puede ser alcanzado es de 1500 y en WLAN (802.11) el MTU máximo es de 2304. 

## Path MTU Discovery
Path MTU Discovery se refiere a una técnica para determinar el MTU máximo que puede ser alcanzado entre el punto de origen de la solicitud hacía su destino. Veamos un ejemplo de esto para entender mejor su funcionamiento:

Imaginemos que tenemos una computadora con conectividad via Ethernet (MTU 1500). Queremos trasladar un paquete con un tamaño de datagrama de 3000. Con solo estos datos y, suponiendo que los routers intermediarios tienen un MTU de 1500, podemos determinar que se necesitará fragmentar el paquete en 3 (1er paquete con 20 bytes de header + 1480 bytes de la información a enviar, 2ndo paquete con con 20 bytes de header + 1480 bytes de la información a enviar y el 3er paquete con 20 bytes de header y 20 bytes de la información a enviar). 

Sin embargo, para enviar el paquete no podemos solo suponer que los routers intermedios tengan esa capacidad de MTU para transferir los datos. Para resolver esta incognita, el Path MTU discovery manda primero una request por todo el path para determinar el MTU de cada router intermedio hasta llegar al host final. De esta forma si algun router intermedio no tuviera la capacidad mínima con la cuál se enviará el paquete (recordemos, 1500 MTU), desde la trasmisión de los datos del host solicitante se podría adaptar el MTU al mínimo encontrado en el path y fragmentar los paquetes correspondientemente. 

Veamos otro ejemplo utilizando ahora el Path MTU Discovery:

El host A, con un MTU de 4000, desean enviar un paquete al host B con un MTU desconocido. Antes de iniciar la transferencia de datos, el MTU Path Discovery determina que hay 4 routers intermedios con los siguientes MTU:

- Router 1: 5000 MTU
- Router 2: 1500 MTU
- Router 3: 3000 MTU
- Router 4: 2000 MTU
- Host B: 500 MTU

Basado en lo que se logró descubrir por medio del Path MTU Discovery, podemos determinar que para transferir X cantidad de datagramas, el host A deberá adaptar su MTU al mínimo encontrado (500 MTU) y proceder a fragmentar el paquete en X cantidad de fragmentos necesarios para la transferencia total. 
