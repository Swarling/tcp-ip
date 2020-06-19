---
layout: default
title: Ruteo Estático
nav_order: 27
permalink: /ruteo-estatico

---

##### **Autores:** Swarling A. González

##### **Fecha de creación:**  19/06/2020

##### **Revisiones:** 

{: .no_toc }

##### **Fecha de revisión:** 

{: .no_toc }

# RUTEO ESTÁTICO

{: .no_toc }

#### Contenido:

{: .no_toc}

{:toc}

---


## Resumen

El ruteo estático es una forma de configurar el reenvío de paquetes en un router de forma manual, puesto que una ruta estática tiene una AD de 1 esta será la primera opción que toma el router para el reenvío de paquetes, no es recomendable utilizarlas si se desea comunicar múltiples redes, para se recomienda usar enrutamiento dinámico, ya que todo el proceso de selección de rutas se realizará de forma automática.


## ¿Qué es Ruteo Estático?

Esto se refiere a rutas estáticas las cuales son almacenadas en la tabla de enrutamiento de un router el cual usa para el reenvío de paquetes, son configuradas en un router de forma manual para que así el equipo tenga conocimiento de una red por medio de la ruta que le configura manualmente.

Esta es una buena solución para redes pequeñas por su seguridad y economía, puesto que no consume mucho ancho de banda, no hace trabajar al CPU del router y es muy fácil de configurar.

## Rutas Estáticas

Son rutas que especifican el camino que tomarán los paquetes que provengan de una red y estén dirigidos a esta. De esta forma se garantiza la ruta que tomarán ciertos paquetes, a diferencia de las rutas dinámicas de las cuales no tenemos tanto control.

La Principal diferencia entre estas dos es que las rutas estáticas se deben de ingresar de forma manual y no son aprendidas automáticamente como lo son las rutas dinámicas, esto se dificulta si hay una red grande, por lo cual se recomienda solo usar rutas dinámicas si lo que se quiere lograr es una comunicación con múltiples redes.

## Parámetros

Cuando se quiere configurar enrutamiento estático se debe de tener conocimiento de lo siguiente:

**Red**

Se Refiere a la red que se desea poder alcanzar.

**Máscara**

Es la mascara de la red, dicho de otra forma es la que nos proporciona la cantidad de hosts (equipos).

**Dirección De Siguiente Salto**

Es la dirección IP por la que está conectado el otro equipo a nosotros, es decir, si tenemos dos routers (R1, R2) conectados por la interfaz ethernet en R1 con (192.168.1.1/24) y R2 con (192.168.1.2/24) si estamos en R1 la dirección del siguiente salto seria 192.168.1.2 y viceversa.

**Interfaz**

Este parámetro es usado cuando no se conoce la dirección de siguiente salto se configura la interfaz como salida del paquete.

**Distancia Administrativa (AD)**

Es una medida que usan algunos router (Cisco) para seleccionar la mejor ruta cuando hay mas de un camino o ruta hacia un mismo destino, por lo defecto una ruta estática tiene una Distancia Administrativa de 1, es decir que si hay otra ruta hacia un equipo y ese tiene una ruta estática configura el router preferirá reenviar el paquete por donde está la ruta estática configurada.



## Configuración en Router Cisco

En los router Cisco hay dos forma de configurar una ruta estática, ya sea por una interfaz grafica o por CLI

la configurar la ruta estática se debe de ingresar al modo de configuración global, posteriormente escribir lo siguiente:	

**Router(config)#ip route (Red Destino) (Macara) (Siguiente Salto / Interfaz) (AD)**

Por lo genera en cualquier equipo que se desee configurar una ruta estática nos proporcionará ya sea una interfaz grafica para hacerlo pero los datos solicitados son los mismos: **(Red Destino) (Mascara) (Gateway o Siguiente Salto)**


​	