---
layout: default
title: Capa de enlace de red
nav_order: 16
permalink: /link-layer
---
##### **Autores:** Herbert Dávila
{: .no_toc }

##### **Fecha de creación:** 19 de Junio 2020
{: .no_toc }

##### **Revisiones:** 
{: .no_toc }

##### **Fecha de revisión:** 
{: .no_toc }

# Capa de enlace de red
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


#  **Resumen**
La segunda capa del Modelo de referencia OSI es la capa de enlace de datos, Traduce los binarios (o BIT) en una unidad de datos llamada "trama" y permite que las capas superiores accedan a los medios.

#  **Link Layer**
La capa de enlace de datos, a veces también llamada *capa de enlace* es donde muchas tecnologías de redes de área local (LAN) cableadas e inalámbricas funcionan principalmente.

![Data Link Layer](../../../../../Desktop/DLL.JPG)

La capa de enlace de datos a menudo se divide conceptualmente en dos subcapas: *control de enlace lógico (LLC)* y *control de acceso a medios (MAC)* . Esta división se basa en la arquitectura utilizada en el Proyecto IEEE 802. Al separar las funciones LLC y MAC, la interoperabilidad de diferentes tecnologías de red se hace más fácil

La capa de enlace de datos mueve bits a través del enlace y puede agregar confiabilidad a la computadora sin procesar enlace de comunicaciones. La capa de enlace de datos puede ser muy simple o hacer que el enlace parezca un error. La capa de enlace de datos generalmente agrega un encabezado y avance a los datos presentados por la capa de red.

Cuando se desarrolló Ethernet por primera vez, funcionaba solo en modo hald-duplex utilizando un cable compartido. Es decir, los datos podrían enviarse solo de una manera a la vez, por lo que solo una estación estaba enviando una trama en un momento dado. Con el desarrollo de Switched Ethernet, la red ya no era una sola pieza de cable compartido, sino muchos conjuntos de enlaces. Como resultado, múltiples pares de estaciones podrían intercambiar datos simultáneamente. Además, Ethernet se modificó para operar en Full dúplex, deshabilitando efectivamente los circuitos de detección de colisión. Esto también permitió ampliar la longitud física de Ethernet, porque se eliminaron las restricciones de tiempo asociadas con la operación semidúplex y la detección de colisiones.

## **Funciones de la capa de enlace de datos**
Las siguientes son las tareas clave realizadas en la capa de enlace de datos: 

## **Aspectos a los que se enfoca Link Layer**



### **Control de enlace lógico (siglas en ingles LLC):**

 El control de enlace lógico se refiere a las funciones requeridas para el establecimiento y control de enlaces lógicos entre dispositivos locales en una red. Esto generalmente se considera una subcapa DLL; proporciona servicios a la capa de red que se encuentra por encima y oculta el resto de los detalles de la capa de enlace de datos para permitir que diferentes tecnologías funcionen sin problemas con las capas superiores. La mayoría de las tecnologías de red de área local utilizan el protocolo IEEE 802.2 LLC.

### **Control de acceso a medios (MAC):**

se refiere a los procedimientos utilizados por los dispositivos para controlar el acceso al medio de la red. Dado que muchas redes usan un medio compartido (como un solo cable de red o una serie de cables que están conectados eléctricamente a un único medio virtual) es necesario tener reglas para administrar el medio para evitar conflictos. Por ejemplo. Ethernet usa el método CSMA / CD de control de acceso a medios, mientras que Token Ring usa el paso de tokens. 

- #### **Trama de datos:** 

  La capa de enlace de datos es responsable de la encapsulación final de los mensajes de nivel superior en *tramas* que se envían a través de la red en la capa física. 

- #### Direccionamiento: 

  La capa de enlace de datos     es la capa más baja en el modelo OSI que se refiere al direccionamiento:     etiquetar información con una ubicación de destino particular. Cada     dispositivo en una red tiene un número único, generalmente llamado *dirección     de hardware* o *dirección* *MAC*, que es utilizado por el     protocolo de capa de enlace de datos para garantizar que los datos     destinados a una máquina específica lleguen correctamente. 

- #### **Detección y manejo de errores:** 

  La capa de enlace de datos maneja los errores que ocurren en los niveles inferiores de la pila de red. Por ejemplo, a menudo se emplea un campo de verificación de redundancia cíclica (CRC) para permitir que la estación que recibe datos detecte si se recibió correctamente


