---
layout: default
title: Red de control para automóviles basada en Ethernet
nav_order: 13
permalink: /ethernet-automovil
---
##### **Autores:**
{: .no_toc } 

Dennis Mejicanos

##### **Fecha de creación:** 05-06-2020
{: .no_toc }

##### **Revisiones:**  Nombre Apellido, Nombre Apellido
{: .no_toc }

##### **Fecha de revisión:** 20-20-2020
{: .no_toc }

# Red de control para automóviles basada en Ethernet
{: .no_toc }

#### Contenido:
{: .no_toc }

1. TOC
{:toc}

---


## Resumen
Durante las ultimas dos décadas el uso de redes para la comunicación entre los dispositivos electrónicos de control han aumentado en la industria automotriz. Se utiliza Ethernet para integrar funciones de control en tiempo real y entretenimiento. Se simulan dos escenarios principales utilizando OPNET. El primero se utiliza para simular únicamente redes de control en un vehículo en movimiento. El segundo es igual al primero pero se le agrega una carga de video para simular entreteniendo en un vehículo en movimiento. Ambas simulaciones fueron exitosas, ya que las demoras en las redes de control estaban por debajo por las demoras máximas requeridas por el sistema.

## Introducción

El uso de redes entre las unidades de control electrónico (ECU) en la industria automotriz no es algo relativamente nuevo, si no que a principios de los años noventa se empezó a utilizar toda esta tecnología.  Sistema antibloqueo de frenos (ABS), Estabilidad Electrónica Programada (ESP), Dirección asistida eléctrica (EPS), Freno por cable y mas funciones disponibles hoy en día fueron elaboradas por la alta fiabilidad del hardware de los componentes que fueron integrados a la fabricación de automóviles. Mas funciones fueron incluidas pero en el área de entretenimiento como por ejemplo: DVD, manos libres para las llamadas por teléfono, navegación por GPS . Pero la principal idea es la de reemplazar sistemas por completos que utilizan cables, por microcontroladores, y computadoras para obtener una mayor seguridad y mejor manejo. Debido a esto el estudio se divide en 3 fases:

1. Sistemas por cable
2. Redes Multimedia
3. Modelo Sugerido



## Sistemas por cable
Los sistemas por cable en algún momento podrán reducir grandes velocidades a practicante estar parados en cuestión de segundos y sin necesidad de alguna acción humana, todo esto será posible por sistemas de posicionamiento incorporados, sensores para detectar el estado de la carretera, y sensores para determinar si existen automóviles cerca y así poder determinar un camino mas seguro, harán que viajar en automóvil sea mucho mas seguro y eficiente. Todos los cálculos serán hechos por una computadoras que poseerá el automóvil en su interior. Actualmente todos estos sistemas se están utilizando en automóviles Diesel para así poder regular la cantidad de gasolina consumida y la velocidad con la que viaja, así como también el sistema de dirección frontal por cable que elimina la conexión mecánica entre las ruedas delanteras de un vehículo y el conductor, y el sistema actúa por si solo. La seguridad y la estabilidad son el corazón del impulso para desarrollar tecnología automotriz por cable, especialmente para una combinación de dirección y frenado.

## Redes Multimedia

Muchos protocolos han sido adaptados específicamente para transmitir una gran cantidad de datos, los cuales son necesarios en las aplicaciones multimedia en sistemas automotrices. Principalmente son:

- MOST
- IDB-1394

### MOST

Proporciona datos de audio y video punto a punto con una taza de transferencia de 24.8Mbps. Este protocolo esta orientada hacia aplicaciones como radios, sistemas de posicionamiento global (GPS), pantallas de video y sistemas de entretenimiento. 

### IDB-1394

Es una versión automotriz de IEEE 1394 para el sistema interno del vehículo. Ofrece una taza de transferencia de 100 Mbps por par trenzado, con un numero máximo de 63 dispositivos integrados para toda la funcionalidad del automóvil por medio de los sistemas por cable.

## Modelo Sugerido

El modelo sugerido esta construido por medio de conmutadores Ethernet, esto es porque la necesidad de diferentes redes para cada solicitud del vehículo en movimiento. Cada red tiene un protocolo distinto. Por lo tanto se utiliza CAN, este sistema se mostro mas robusto y con mejor rendimiento desde su aparición, y esta orientado en acomodar las señales de control del vehículo. Esto dará lugar a que mas funciones se puedan agregar al sistema para aumentar la comodidad de los pasajeros. Esto es integrando el control de trafico del tren motriz, el chasis y la carrocería, por ejemplo con multimedia y HMI. Se utilizo OPNET como herramienta de simulación para este estudio.

## Resultados

Se simularon dos escenarios. El primero únicamente incorpora nodos de control: sensores, actuadores y controladores. Los datos se originan en los nodos del sensor, viajan sobre la red para llegar al controlador. En el controlador, la acción se calcula y se envía nuevamente a través de la red para llegar al actuador. La red esta construida en topología de estrella.

El segundo escenario es similar al primero, pero se incluyo un trafico adicional de video. Una terminal de video simulando el nodo de entretenimiento del vehículo con DVD. Este nodo se comunica nuevamente con el controlador central que es el responsable de entregar el video a esa terminal. En otras palabras, la controladora es la encargada de procesar el control del vehículo, así como de video para el entretenimiento. El propósito de este escenario es descubrir si es posible usar una sola red para incluir todo tipo de controladores del vehículo con carga de entretenimiento.

## Conclusión

Ante la exigente necesidad actual sobre el ancho de banda para multimedia y entretenimiento a bordo de vehículos en movimiento, Ethernet presenta una solución atractiva después de sus resultados en entretenimiento y control sobre un vehículo en movimiento. Los Resultados de las simulaciones demostraron que el esquema propuesto es factible como un punto de inicio para la investigación para el sistema propuesto. Se necesita una investigación mas profunda para centrarse en los posibles problemas que puedan surgir de EMI.