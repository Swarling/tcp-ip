---
layout: default
title: Modelos de Arquitectura de Red
nav_order: 12
permalink: /modelos-arquitectura-red
has_toc: false
---
##### **Autores:** 
{: .no_toc }
[Santiago Wever](https://github.com/sweverG)

[Herbert Dávila](https://github.com/hjdgua)

[Julio Guzmán](https://github.com/enlaetapad)

##### **Fecha de creación:** 
{: .no_toc }

##### **Revisiones:**  
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Modelos de Arquitectura de Red
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
Los modelos OSI y TCP/IP son estándares que tienen por objetivo conseguir interconectar sistemas que necesiten intercambiar información.

La arquitectura de estos modelos es una división por capas, cada capa tiene una función distinta y cada capa cuenta con protocolos que implementan diferentes procesos. La finalidad de los modelos es ordenar el proceso de comunicación entre sistemas y permitir la interconexión de los mismos.

## Modelo OSI

El modelo de interconexión de sistemas abiertos, también llamado **OSI** (en inglés *open system interconnection*) es el modelo de red descriptivo propuesto por la Organización  Internacional para la Estandarización (ISO) en el año 1977 y aprobado en el año 1984.

Es una normativa formada por **siete capas** que  define las diferentes fases por las que deben pasar los datos para  viajar de un dispositivo a otro sobre una red de comunicaciones.

Constituye por tanto un marco de referencia para la definición de arquitecturas de interconexión de sistemas de comunicaciones.


7) Aplicación: La capa que interactua con el usuario. Aplicaciones web y navegadores utilizan protocolos de esta capa.

6) Presentación: Traduce lo que la información de nivel de aplicación a nivel de red y viceversa.

5) Sesión: Establece y termina las conexiones.

4) Transporte: Coordina la transferencia de datos.

3) Red: Determina la forma que serán enviados los datos.

2) Enlace de Datos: Traduce los bits a señales para que puedan ser accesibles.

1) Física: Es el hardware que transmite las señales.



## Modelo TCP/IP
El desarrollo del modelo TCP/IP de 4 capas inició antes de que comenzara el trabajo del modelo OSI de 7 capas. El modelo TCP/IP también se conoce como el conjunto de protocolos TCP/IP, el conjunto de protocolos de Internet, el stack TCP/IP o el modelo DoD.

El desarrollo del modelo TCP/IP comenzó de forma paulatina en la década de 1970,  los siguientes hechos son importantes en el desarrollo del modelo:

- ARPANET, el precursor de Internet, se desarrolla a finales de la década de 1960.
- En mayo de 1974, Kahn y Cerf publicaron un documento titulado "Un protocolo para la intercomunicación de redes de paquetes", que describía las primeras ideas de lo que se convertiría en el modelo TCP/IP.

- En marzo de 1982, el Departamento de Defensa de los Estados Unidos declaró que TCP/IP era el estándar para todas las redes de computadoras militares.

- El 1 de enero de 1983 (conocido como "Día de la bandera"), ARPANET cambió del antiguo protocolo de red NCP, a TCP/IP.

El modelo OSI nunca se implementó realmente, pero la teoría que incorpora ha influido y continua influyendo en el desarrollo de las redes. 

El modelo TCP/IP es la base de la mayoría de las redes de comunicación modernas. 

El nombre del modelo TCP/IP incluye dos protocolos muy importantes: Transmission Control Protocol (TCP) e Internet Protocol (IP). Sin embargo, el modelo va más allá de estos dos protocolos y por medio de un enfoque de capas, puede mapear casi cualquier protocolo que se utiliza actualmente en la comunicación.

En su definición original, el modelo TCP/IP incluía cuatro capas, donde cada una de las capas proporcionaría transmisión y otros servicios para el nivel superior:

- Capa de Aplicación
- Capa de Transporte 
- Capa de Internet
- Capa de enlace de datos

En su definición más moderna, la capa de enlace se divide en dos capas adicionales para separar el enlace físico de los servicios y protocolos incluidos en esta capa. La capa de Internet también se denomina a veces capa de red basándose en el modelo OSI.

![Comparacion Modelos OSI y TCP/IP](https://cjs6891.github.io/el7_blog/public/img/1514082772.png)

Las capas de ambos modelos pueden compararse cómo se muestra en la imagen anterior.

Las capas en el modelo original TCP/IP tiene las siguientes atribuciones:

- Capa de enlace: la capa de enlace incluye el hardware y los protocolos necesarios para enviar información entre dos hosts que están conectados por un enlace físico (por ejemplo, un cable) o por aire (por ejemplo, a través de ondas de radio). En la capa de enlace, la unidad de protocolo se denomina trama.


- Capa de Internet: la capa de Internet proporciona servicios de red e incluye protocolos que permiten la transmisión de información a través de múltiples redes. En la capa de Internet, la unidad de protocolo se llama paquete.


- Capa de transporte: la capa de transporte proporciona servicios para transferir con éxito información entre dos puntos finales. Esta capa se preocupa por el proceso de extremo a extremo y la unidad de protocolo se denomina segmento.


- Capa de aplicación: la capa de aplicación es la capa superior y es la más familiar para los usuarios finales ya que integra los protocolos de aplicación que utilizan las aplicaciones de los usuarios finales.

El proceso de encapsulación de desencapsulación utilizando el modelo TCP/IP para el envío de un mensaje HTTP se muestra en la siguiente imagen:

![Encapsulacion y desencapsulacion](https://cjs6891.github.io/el7_blog/public/img/1514083207.png)

## Referencias

1. [Modelo de arquitectura del protocolo TCP/IP](https://docs.oracle.com/cd/E19957-01/820-2981/ipov-10/)
2. [Internet Protocol Suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)

3. [TCP/IP Model](https://cjs6891.github.io/el7_blog/texts/cisco-ccna-cyber-ops-secfnd-1/#TCP/IP%20Model)