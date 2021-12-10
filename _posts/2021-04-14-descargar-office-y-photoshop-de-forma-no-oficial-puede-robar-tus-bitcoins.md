---
layout: post
title: Descargar Office y Photoshop de forma no oficial puede robar tus Bitcoins
description: Yo estoy seguro que la mayoría de las personas que ingresen a este blog
  van a tener instalado Linux, pero aún así valía la pena escribir un artículo sobre
  este tema. Descargar Photoshop y Office de manera ilegal puede terminar en un
  desastre.
date: 2021-04-14T03:00:00.000+00:00
image: https://images.unsplash.com/photo-1516245834210-c4c142787335?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=869&q=80
tags:
- Noticias
- Seguridad
- Windows

---
Yo estoy seguro que la mayoría de las personas que ingresen a este blog van a tener instalado Linux, pero aún así valía la pena escribir un artículo sobre este tema. Descargar Photoshop y Office de manera ilegal puede terminar en un desastre.

Desde el surgimiento del software comercial, múltiples desarrolladores se han dedicado a la creación y lanzamiento de cracks y parches, términos que se refieren a aplicaciones simples y fáciles de usar que permiten a los usuarios esquivar los mecanismos anti-piratería en estos productos para utilizarlos sin tener que pagar.

Los principales problemas de esta práctica tienen que ver con la violación de legislaciones de propiedad intelectual, aunque recientemente han aumentado los reportes de incidentes de seguridad relacionados con el uso de software **“crackeado”**.

Un reciente reporte de la firma de seguridad `BitDefender` hace referencia al descubrimiento de una serie de ataques basados en la **explotación de fallas de seguridad** en versiones piratas de `Microsoft Office` y algunas herramientas para la edición de imágenes como el popular `Photoshop`. Estos ataques buscan **tomar control de los dispositivos afectados** para secuestrar carteras de criptomonedas y extraer información de forma inadvertida a través de la red `Tor`.

Al ejecutarse en el sistema comprometido, el software crackeado entrega una instancia de `ncat.exe`, **una herramienta de envío de datos sin procesar a través de la red, además de un proxy Tor**. Estos archivos se colocan en el almacenamiento del sistema identificados como `%syswow64%\nap.exe` o `%syswow64%\ndc.exe`, y `%syswow64\tarsrv.exe`. También se coloca un archivo por lotes en `%syswow64%\chknap.bat` que contiene una línea de comandos para el componente Ncat dedicado a recorrer los puertos 8000 y 9000 en dominios .onion como se muestra a continuación.

[](https://noticiasseguridad.com/nsnews_u/2021/04/bitdefender01.jpg)

FUENTE: BitDefender

Estas herramientas trabajan en conjunto para la creación de un **peligroso backdoor** conectado al servidor C&C de los atacantes a través de la red `Tor`. **El binario ncat usa el puerto listener del proxy Tor** y usa el estándar -exec, que permite que **todas las entradas del cliente sean enviadas a la aplicación correspondiente** y las respuestas se envíen al cliente a través del socket del mismo modo que un shell inverso.

Este **software malicioso** también crea mecanismos de persistencia para el archivo proxy TOR y el binario Ncat en la máquina comprometida con **un servicio programado que se ejecuta cada 45 minutos**. Los expertos de `Bitdefender` mencionan que es altamente probable que el _backdoor_ sea empleado por **un operador humano** en lugar de enviar solicitudes automatizadas a las víctimas.

![](https://noticiasseguridad.com/nsnews_u/2021/04/bitdefender02.jpg)

FUENTE: BitDefender

Algunas de las tareas maliciosas detectadas por los expertos incluyen:

* Extracción de archivos
* Ejecución del cliente BitTorrent
* Inhabilitación del firewall
* Robo de billeteras Monero a través del cliente CLI legítimo “monero-wallet-cli.exe”

Un reporte más amplio, además de los indicadores de compromiso encontrados por los expertos, están disponibles en la plataforma oficial de Bitdefender. Para conocer más sobre riesgos de seguridad informática, malware, vulnerabilidades y tecnologías de la información, no dude en ingresar al sitio web del Instituto Internacional de Seguridad Cibernética (IICS).

[Fuente](http://localhost:1313/posts/descargar-office-y-photoshop-de-forma-no-oficial-puede-robar-tus-bitcoins/Fuente)
