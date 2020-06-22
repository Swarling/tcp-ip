---
layout: default
title: TCP - Control de Flujo
nav_order: 35
permalink: /control-de-flujo

---

##### **Autores:** Juan Carlos Guzman

{: .no_toc }


##### **Fecha de creación:** 19 Junio 2020

{: .no_toc }

##### **Revisiones:** 

{: .no_toc }

##### **Fecha de revisión:** 

{: .no_toc }

# CONTROL DE FLUJO EN TCP

{: .no_toc }

#### Contenido:

{: .no_toc }

1. TOC

{:toc}

---


## Resumen

TCP proporciona mecanismos para el control del flujo. El control del flujo permite mantener la confiabilidad de la transmisión de TCP  mediante el ajuste de la velocidad del flujo de datos entre el origen y  el destino para una sesión dada.


## Control de Flujo en TCP

TCP utiliza control de flujo para evitar que un emisor envié datos de forma más rápida de la que el receptor puede recibirlos y procesarlos. El control de flujo se ha vuelto indispensable en redes en las que se comunican dispositivos con distintas velocidades de transferencia. Por ejemplo, si una Computadora envía datos a un dispositivo móvil que procesa los datos de forma lenta, el dispositivo móvil debe regular el flujo de datos.

TCP usa una ventana deslizante (Sliding Window) para el control de flujo. En cada segmento TCP, el receptor especifica en el campo RECEIVE WINDOW, la cantidad de bytes que puede almacenar en el buffer para esa conexión. El emisor puede enviar datos hasta esa cantidad. Para poder enviar más datos debe esperar que el receptor le envié un ACK con un nuevo valor de ventana.



- El receptor lee los datos más despacio de que los recibe.
- De lo contrario, el buffer se desbordaría
- El receptor informa al emisor del espacio libre en el buffer.

## Stop-and-Wait

En este método, el receptor indica su disposición a recibir los datos para cada  trama, el mensaje se divide en múltiples frames. El emisor espera por un ACK (reconocimiento) después de recibir cada frame por un tiempo especificado  (llamado tiempo de espera). 

Se envía un paquete para verificar que el receptor ha recibido el frame correctamente. Una vez recibido el ACK, se envía el siguiente frame.  

Operaciones 

1. Emisor: Transmite un solo frame a la vez.

2. Receptor: Transmite acuse de recibo (ACK), cuando haya recibido el frame.

3. Remitente recibe ACK dentro de tiempo de espera.

4. Regresa al paso 1.

Si no se recibe un ACK durante la transmisión, entonces tiene el frame tendrá que ser reenviado por el emisor. Este proceso se conoce  como retransmisión ARQ (petición de repetición automática).  El problema con Stop-and-Wait es que sólo un frame se puede  transmitir a la vez, y que constantemente esto conduce a la transmisión  ineficiente, ya que hasta que el emisor recibe el ACK no puede transmitir cualquier nuevo paquete. Durante este tiempo tanto el emisor y el canal no son utilizados. 

# Ventana Deslizante

El protocolo TCP utiliza un mecanismo llamado Ventana Deslizante que es  del tipo "Stop and Wait", esto quiere decir que el emisor deja de enviar paquetes hasta que reciba un mensaje de reconocimiento que le llegaron  los datos por parte del receptor. Podemos deducir a partir de esto que  es una comunicación poco eficiente, ya que si el receptor no envía el  reconocimiento no se puede seguir transmitiendo.

La Ventana Deslizante está compuesta por dos "Ventanas", la primera es la **Ventana de recepción**, ubicada en el receptor, y que indica cuantos  bytes caben aún en el buffer que se utilice en el receptor. La segunda  "ventana" es la **Ventana de envío**, la que indica Qué bytes del  buffer de envío se pueden enviar sin tener que esperar una confirmación. 

![](https://www.tutorialspoint.com/data_communication_computer_network/images/stop_and_wait_arq.jpg)

Analizando la imagen, hay una ventana de envío ubicada al comienzo del buffer de envío.  Se envía el Frame0. Al recibirlo, nuestro receptor envía una  confirmación ACK0, confirmando que recibió satisfactoriamente el  Frame0. El emisor, al recibir este ACK0, sabe que recibió con éxito el  primero, por lo que desliza la ventana el espacio correspondiente al  tamaño del paquete. Luego hace envío del paquetes 1. Como el cliente los pudo recibir, envía ACK1, lo que hace que el servidor de envío deslice la ventana 1 espacio por el ACK1.