---
layout: default
title: TCP
nav_order: 34
permalink: /tcp
---
##### **Autores:** Nelson Cortez
{: .no_toc }


##### **Fecha de creación:** 17/06/2020
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# TCP
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
Transmission Control Protocol (Protocolo de Control de Transmisión) es uno de los protocolos mas importantes de Internet. Fue creado entre los años 1973 y 1974 por Vint Cerf y Robert Kahn.

Permite crear conexiones entre programas de redes de datos compuestas por computadoras, dichas conexiones permitirán el flujo de datos entre los programas, garantizando que los datos serán entregados a su destino sin errores y en el mismo orden en el que fueron transmitidos. 

Utiliza los puertos como un mecanismo para diferenciar las distintas aplicaciones de una máquina, como podrían ser: navegadores o clientes FTP, o aplicaciones que utilizan protocolos como HTTP, SSH, FTP y SMTP.


## Funciones de TCP
En el suite de protocolos TCP/IP, TCP se encuentra en la capa de transporte que está ubicada entre el protocolo de red y el protocolo de aplicación. 

## ![](C:\Users\nelso\OneDrive - Universidad Galileo\Trimestre Actual\PRC. TCPIP\Img Git\Modelo TCPIP.PNG)

A pesar de que TCP trabaja con los servicios de la capa IP que no es confiable, provee dicha confiabilidad en la comunicación entre las aplicaciones, asegurando que los datos emitidos por el cliente sean recibidos por el servidor sin errores y en el mismo orden que fueron enviados. Es un protocolo orientado a la conexión, en la que tanto el cliente como el servidor deben anunciarse y aceptar la conexión antes de empezar a transmitir los datos hacía su destino.

## Características
Los segmentos provenientes del protocolo IP son colocados en orden.

Puede monitorear el flujo de datos para evitar la saturación de la red.

Permite formar los datos en segmentos de longitud variada para ser entregados al protocolo IP.

Multiplexa los datos provenientes de diferentes fuentes para que puedan circular por la red simultáneamente.

## Formato de los segmentos TCP

Los paquetes de bits que constituyen las unidades de datos del protocolo (PDU) TCP son llamados segmentos, está compuesto por los datos enviados desde la capa de aplicación y la header añadido por el protocolo de transporte. Los segmentos TCP son encapsulados en un paquete IP para ser enviados por la capa de red.

![](C:\Users\nelso\OneDrive - Universidad Galileo\Trimestre Actual\PRC. TCPIP\Img Git\Segmento.png)

### Campos del header TCP

- **Puerto origen (16 bits)**: Puerto del emisor

- **Puerto destino (16 bits)**: Puerto del receptor

  Los puertos de origen y destino nos permiten identificar a las aplicaciones emisora y receptora, junto con las direcciones IP del emisor y del receptor utilizadas para crear la conexión. Entre todas las conexiones TCP en Internet, es el socket (combinación de una dirección IP y un puerto) el que permitirá  identificar la conexión TCP única entre los dos extremos.

- **Número de secuencia (32 bits)**: Identifica el byte del flujo de datos enviado por el emisor TCP al receptor TCP.

  Cuando una conexión se establece, la bandera SYN se activa, consumiendo así un número de frecuencia, por lo que el número de secuencia del primer byte de datos será el ISN+1. El ISN (initial sequence number) se encuentra en el campo del número de secuencia elegido por el host para esa conexión.

- **Número de acuse de recibo (32 bits)**: Valor del siguiente número de secuencia que el emisor del segmento espera recibir.

  Cuando se establece una conexión, este número se envía siempre que la bandera ACK está activa.

- **Longitud de cabecera (4 bits)**: tamaño de la cabecera en palabras de 32 bits.

- **Reservado (3 bits)**: Para su uso futuro. Debe estar a 0.
- **Banderas (9 bits)**:
  - **NS (1 bit)**: ECN-nonce concealment protection. Protección contra paquetes accidentales o maliciosos.
  - **CWR (1 bit)**: Congestion Window Reduced. Se activa por el emisor para indicar que ha recibido un segmento con la bandera ECE activado y ha respondido con el mecanismo de control de congestión.
- **Tamaño de la ventana o ventada de recepción (16 bits)**: Especifica el máximo número de bytes pendientes de asentimiento. Es un sistema de control de flujo.
- **Suma de verificación (26 bits)**: Checksum. Se utiliza para comprobar errores en la cabecera o los datos.
- **Puntero urgente (16 bits)**: Cantidad de bytes desde el número de secuencia que indica el lugar donde acaban los datos urgentes.
- **Opciones**: Permite añadir características no cubiertas por el header fijo.
- **Relleno**: Para asegurar que el header termine con un tamaño múltiplo de 32 bits.

# ¿Cómo funciona el protocolo TCP?

Las conexiones TCP se componen de 3 etapas:

1. 3-way handshake: Permite establecer la conexión.
2. Tranferencia de datos.
3. Fin de la conexión.

## Establecer la conexión

La conexión se establece con un procedimiento de negociación de 3 pasos (3-way handshake).

Normalmente una de las entidades abre un socket en determinado puerto TCP y se queda a la escucha de nuevas conexiones (apertura pasiva). 

1. El cliente realiza una apertura activa enviando un paquete SYN inicial al servidor . 
2. El servidor comprueba que el puerto esté abierto para verificar que el dispositivo de destino tenga ese servicio activo y está aceptando peticiones en ese puerto.
   - Si el puerto no está abierto, se envía al cliente un paquete de respuesta con el bit RST activo, indicándole de esta forma que el intento de conexión fue rechazado.
   - Si el puerto está abierto, el servidor envía al cliente un paquete SYN/ACK.
3. El cliente responderá al servidor con un paquete ACK, completando de está forma el 3-way handshake.

> El número de secuencia generado por cada lado ayuda a que no se produzca spoofing.

![](C:\Users\nelso\OneDrive - Universidad Galileo\Trimestre Actual\PRC. TCPIP\Img Git\3-way handshake.png)



## Transferencia de datos

Se realizan mecanismos claves para determinar la fiabilidad y robustez del protocolo: 

**Número de secuencia**: Identifican los datos dentro del flujo de bytes. Se utiliza para ordenar los segmentos TCP recibidos y detectar posibles paquetes duplicados. Se intercambian entre ambas entidades. 

Los segmentos TCP incluyen un par de números de secuencia: El número de secuencia (emisor) y el número de asentimiento (receptor). El receptor asiente los segmentos TCP indicando que ha recibido una parte del flujo de bytes. 

El asentimiento selectivo (Selective Acknowledgement, SACK) permite a un receptor TCP asentir los datos recibidos para que el remitente solo retransmita los segmentos de datos faltantes.

**Checksums**: Permiten detectar errores, asentimientos y temporizadores para detectar pérdidas o retrasos. Utiliza la suma en complemento a uno.



**Asentimientos y temporizadores**: Los ack de los datos enviados o los faltantes son usados por los emisores para interpretar las condiciones de la red entre el emisor y el receptor TCP. Junto con los temporizadores, éstos pueden alterar el comportamiento del flujo de datos, con el fin de evitar la congestión en la red. Entre ellos se incluyen el uso de ventana deslizante (controla que se mande información dentro de los límites del búfer del receptor) y algoritmos de control de flujo.

**Ventanas deslizantes**: Para el control del flujo de datos. El fin es evitar que el emisor envíe datos de forma más rápida de la que el receptor los puede recibir y procesar. En cada segmento TCP, el receptor especifica la cantidad de datos que puede almacenar en el búfer para esa conexión, por lo que el emisor solo puede enviar hasta esa cantidad de datos.



## Fin de la conexión

Se utiliza una negociación en cuatro pasos (4-way handshake) para terminar la conexión en ambos extremos. También es posible realizar en 3 pasos, enviando el segmento FIN y ACK en uno solo. 

Para parar la mitad de la conexión, se transmite un segmento con la bandera FIN en 1 que será respondido con un ACK. Por lo que una desconexión típica necesita un par de segmentos FIN y ACK desde ambas entidades. 

En caso de que una de las entidades finalice la conexión pero no la otra, el lado que la ha finalizado no podrá enviar mas datos pero la otra entidad si podrá hacerlo.

![](C:\Users\nelso\OneDrive - Universidad Galileo\Trimestre Actual\PRC. TCPIP\Img Git\Connection Termination.png)

# Puertos TCP

Mediante el número de puertos, TCP puede identificar a las aplicaciones emisoras y receptoras. En cada lado de la conexión se tiene asociado un número de puerto (16 bits con signo, dando un total de 65536 puertos posibles) asignado por la aplicación emisora o receptora. Se pueden clasificar en:

1. **Bien conocidos:** Asignados por la IANA (Internet Assiggned Numbers Authority), abarcan desde el 0 al 1023 y suelen usarse por el sistema o por procesos con privilegios. Las aplicaciones que utilizan este puerto se ejecutan como servidores que escuchan conexiones, como podrían ser FTP (21), SSH (22), Telnet (23), HTTP (80), etc.
2. **Registrados**: Suelen utilizarse para aplicaciones temporales de usuario cuando se conectan con los servidores o representar un servicio registrado por un tercero. Abarcan desde el puerto 1024 al 49151.
3. **Dinámicos**/**Privados**: También suelen utilizarse por aplicaciones de usuario. Abarcan desde el puerto 49152 al 65535.
