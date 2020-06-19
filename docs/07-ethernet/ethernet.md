---
layout: default
title: Ethernet
nav_order: 17
permalink: /ethernet
---
##### **Autores:** 
Fernando López - 16001718

##### **Fecha de creación:** 
18 de junio del 2020

##### **Revisiones:**  
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Ethernet
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---

## Resumen

Ethernet es un protocolo que abarca las primeras dos capas del modelo OSI o TCP/IP actualizado el cual considera señales físicas como lógicas, esto contempla tamaños mínimo y máximo de mensaje, identificación de dispositivos, dispositivos de conmutación, codificaciones tanto físicas como lógicas, verificación de errores de transmisión, definición del mensaje (frame o trama) y sus distintas partes entre otros aspectos. Este protocolo no solo permite sino que define la conexión y comunicación entre distintos dispositivos a través de una red. 


## Ethernet

Ethernet es un **estándar o protocolo** en el área de redes de computadoras que contempla las características de conectores, conductores, señales en el nivel de la **capa física**. También contempla los formatos de los frames o tramas en la **capa de enlace de datos**. Ambas capas anteriormente mencionadas, son del modelo OSI o TCP/IP actualizado

## Direcciones
Son direcciones de 48 bits a las que se conoce como **direcciones físicas** o **direcciones MAC**. Estas direcciones son únicas para cada dispositivo de red, los primeros 24 bits es una identificación del fabricante y los últimos 24 bits son determinados por la IEEE. Estas direcciones son utilizadas por los protocolos y dispositivos de capa 2 en el modelo OSI o el modelo TCP/IP actualizado.

## MTU
El MTU (maximum transfer unit) o **unidad máxima de transferencia** es el tamaño de la unidad de datos más grande que se puede enviar a través de un enlace. Al MTU de un camino de varios enlaces se le llama **path MTU** el cual se calcula como el mínimo de los MTUs de todos los enlaces que pertenecen al camino.

## Switches
Es un dispositivo de red que opera en la **capa 2** del modelo OSI y TCP/IP actualizado y su **funcionamiento básico** es que recibe frames y los envía a donde especifica el destino del encabezado del frame, esto lo hace por medio de su **tabla de direcciones físicas** o **filtering table** a la cual agrega un dispositivo cada vez que recibe un frame del mismo.

## Formato del frame Ethernet
Un frame de Ethernet consiste en distintas partes enumeradas a continuación:

- **Preámbulo** (7 bytes): Informa de la llegada de un frame y sirve para sincronizar ambos dispositivos y establecer una misma frecuencia de reloj.
- **SFD o Start frame delimiter** (1 byte): El delimitador de inicio de frame Indica que la dirección física de destino comienza en el siguiente byte.
- **Destino** (6 bytes): Contiene la dirección física para la cual está destinado el frame.
- **Fuente** (6 bytes): Contiene la dirección física del equipo que envió el frame.
- **Largo o tipo** (2 bytes): Si es menor a 1536, el campo especifica el largo del frame en bytes, si es mayor o igual a 1536, este campo especifica el protocolo de la capa superior.
- **P/Q tag** (4 bytes): Si está presente en el frame, este contiene información de identificación de VLAN o VLAN ID, prioridad, la identificación del protocolo y el CFI el cual indica que las direcciones están está en la forma canónica (ethernet) o no canónica (otra).
- **Otros tags o etiquetas** (hasta 482 bytes)
- **Payload o datos** (hasta 1500 bytes): Son los datos que se desea enviar, generalmente provienen de una capa superior.
- **Pad**: Es un grupo de ceros que se agregan al final del payload en caso este no llegara a un tamaño de 1500 bytes, esto con el objetivo de tener un payload de tamaño fijo.
- **FCS o frame checksum** (4 bytes): El frame checksum nos sirve para verificar la integridad del frame (saber si los datos fueron entregados correctamente). Este sistema sirve para detectar errores, no corregirlos.
- **Carrier extension**: Solamente se utiliza en half duplex para mantener compatibilidad con las redes 802.3, este campo sirve para cumplir con el tamaño mínimo de frame de dicho protocolo y de esta manera tener un "espacio" para evitar colisiones entre un frame y otro en un medio compartido.

## Codificación Manchester
La codificación Manchester es un método de codificación de señales eléctricas en el cual, se codifica una señal binaria por medio de flancos en lugar de niveles, por lo que un cambio de nivel bajo a nivel alto es un "0" y un cambio de nivel alto a nivel bajo es un "1". Este método de codificación resulta ineficiente.

## Codificación 4B/5B 
Es un método de codificación lógico en el cual un grupo de 4 bits se traduce a un grupo de 5 bits, por medio de un diccionario predefinido, esto con el objetivo de poder tener más transiciones al momento de transmitir información para poder mantener sincronía entre el emisor y el receptor.

## Codificación MLT
Este método de codificación consiste en tener 3 niveles ya sea voltaje, corriente, etc. Se tiene un nivel positivo, uno negativo y uno neutro o "0", entonces se establece que un cambio de nivel es un "1" y si no cambia de nivel es un "0". Los cambios se hacen en el orden de: positivo, neutro, negativo, neutro y empieza de nuevo.

## Ethernet CRC32
Chequeo o verificación de redundancia cíclica, (cyclic redundancy check) de ethernet es un código destinado a detección de errores en la capa de enlace de datos del modelo OSI o TCP/IP actualizado. Este código tiene un tamaño de 32 bits y se calcula en base al frame o trama en su totalidad y se agrega al mismo, de manera que el equipo receptor pueda calcularlo de nuevo al momento de recibirlo y si el resultado es el mismo, el frame ha llegado a su destino de manera correcta, si llegara a cambiarse un solo bit del frame, el resultado cambiaría. 

## Porque de los tamaños mínimos del frame Ethernet
Los frames tienen un tamaño mínimo de 64 bytes para poder tener una buena detección de colisiones, si los frames fueran más pequeños, algunas colisiones resultarían indetectables. Esto se decidió en las primeras versiones de ethernet donde se utilizaba un cable como un medio compartido a lo largo de distancias grandes, entonces, si se enviaba un frame muy pequeño, se podía comenzar la transmisión de un nuevo frame sin que el anterior hubiera llegado a su destino y de esta manera no se detectarían las colisiones. 

## VLANs
Es un dominio de broadcast (que cualquier nodo puede llegar a todos los otros por medio de broadcast), que está particionado y aislado en una red de computadoras a nivel de capa de enlace de datos del modelo OSI o TCP/IP actualizado. También se puede definir como una red virtual o división, en donde los nodos pueden o no estar conectados físicamente pero si de forma lógica.

## Spanning Tree Protocol
Sirve para traducir cualquier topología entre switches a una topología de árbol, deshabilitando los enlaces que no forman parte de este árbol dejando un solo camino entre todos los pares de nodos, esto con el objetivo de evitar broadcast storm (exceso de tráfico continuo de broadcast o multicast). Si se diera el caso de que uno de los enlaces se cayera, el algoritmo se encarga de definir un nuevo árbol con las nuevas condiciones.

## Compartiendo el medio, CSMA/CD
Es un algoritmo que se utiliza cuando los dispositivos están conectados por un medio compartido y consiste en que antes de enviar información los dispositivos verifiquen si el medio se encuentra disponible. Una vez disponible, se procede a la transmisión del frame o trama y se monitorea si hay colisiones mientras se envía el frame. Si no hay una colisión al completar la transmisión, se procede a restablecer los contadores de retransmisión.

Si se da el caso de una colisión, los dispositivos que la detecten empezarán un temporizador aleatorio antes de retransmitir, si en caso hubiera de nuevo una colisión, el tiempo del temporizador incrementaría.  


## Preguntas

### Pregunta 1
¿Un hub se considera un medio compartido?

### Pregunta 2

¿Que uso tiene la codificación 4B/5B?



## Referencias

- Dordal, P. L. (s. f.). An introduction to computer networks. Recuperado 18 de junio de 2020, de http://intronetworks.cs.luc.edu/1/html/ethernet.html
- Moorthy, V. (1997, 14 agosto). Gigabit Ethernet. Recuperado 18 de junio de 2020, de https://www.cse.wustl.edu/~jain/cis788-97/ftp/gigabit_ethernet/index.html#:~:text=3.1%20Carrier%20Extension,-Gigabit%20Ethernet%20should&text=Carrier%20Extension%20is%20a%20way,considered%20for%20collision%20and%20dropped.
- Jain, R. (s. f.-b). Virtual LANs. Recuperado 18 de junio de 2020, de https://www.cse.wustl.edu/~jain/cis788-97/ftp/h_7vlan.pdf
- Dordal, P. L. (s. f.). An introduction to computer networks. Recuperado 18 de junio de 2020, de http://intronetworks.cs.luc.edu/1/html/ethernet.html
- STP. (2011, 27 junio). Recuperado 18 de junio de 2020, de https://wiki.wireshark.org/STP

