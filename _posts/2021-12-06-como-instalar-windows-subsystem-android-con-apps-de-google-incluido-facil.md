---
layout: post
featured: false
title: Cómo instalar Windows Subsystem Android con Apps de Google incluido (FÁCIL)
description: Después de su anuncio oficial en Junio, por fin podemos probar las aplicaciones
  Android™ en Windows 11. Hoy voy a enseñarte, cómo instalar Android™ con las Gapps
  de Google incluídas,¡en sólo 5 pasos últra sencillos!
date: 2021-12-06T03:00:00.000+00:00
image: https://www.xda-developers.com/files/2021/10/Windows-Subsystem-for-Android-with-Play-Store-Featured-3.jpg
tags:
- Documentacion
- Windows
- Android

---
## Hoy vamos a probar Android™ con las apps de Google

Como ya han de saber, **la mayoría de las personas con Windows 11 ya tienen la posibilidad de probar Android™** en sus computadoras. Sin embargo, tenemos ese problema de que **solo está disponible** (_de manera oficial_) **la tienda de Amazon.**

![](https://docs.microsoft.com/es-es/windows/images/wsa-amazon-appstore.png)

A mi gusto personal, **la tienda de Amazon es un asco**. Y como muchas personas, no nos queda otra que instalar algunas aplicaciones por otro camino.

Hasta hace unos días atras, la manera disponible era, a través de **ADB Sideload**. Esto es, al igual que en Android, utilizando el **Modo Desarrollador** (_Depuración USB / USB debugging_). Para hacer esto, tenemos que bajar la herramienta para poder usar ADB en Windows (algo que ya debería venir pre-instalado). Luego con el modo desarrollador activado, utilizar los comandos de adb para poder mandar el .apk y poder cargarlo en el subsistema de **Android™**. Un proceso un poco largo, y para algunos usarios, tal vez difícil.

***

## Los requisitos mínimos para poder correr Android™

Primero que nada me gustaría darle un breve repaso a los **requisitos mínimos** que son necesarios para poder ejecutar las apps de **Android™** sin problemas.

* **Windows 11** _(con Windows 10 también es posible, pero no me hago responsable de que ahí falle algo)_
* **8GB** o más de **memoria RAM**
* **Intel Core i3** o superior de 8ta generación o **Ryzen 3000+**
* **SSD**
* Virtualización **habilitada** en nuestro equipo

Estos requisitos, son los mínimos. Es posible que algunas aplicaciones o juegos, no te funcionen como en un teléfono Android con 8gb de ram. Más bien, acorde a las especificaciones de tu pc, Android™ correrá mejor o peor.

## Los "cinco" pasos para poder instalar Android™ y las Gapps.

1. El primer, y sencillo, paso es **ir al Repositorio**, de Github, de [**Nageshwar128**](https://github.com/Nageshwar128/WSA-GA-Actions). Y le damos al botón **FORK**.

![](/images/posts/fork.png)

2. Luego en tu repositorio "forkeado". Vas a la pestaña **Acciones** (Actions), presionas en **WSA-GA-Actions** _(el que está del lado izquierdo),_ y le das a **Run Workflow.**
3. En este punto, deben **elegir que GAPPS quieren tener instalado**. Personalmente prefiero las GAPPS pico o nano. Seleccionan la arquitectura del PC y le dan a **Run Workflow**.
4. Una vez finaliza el proceso y aparece **"Complete Job"**. Tenemos que chequear el log y **descargar** el **WSA** desde transfer.sh

![](/images/posts/forkv.png)

5. Y el último paso, como prometí 🤣. Tenemos que **abrir la Powershell como Administrador**.  
   {% highlight bash %}  
   cd Downloads/WSA-gapps # Acá va el directorio donde Extrajiste el .zip  
   Add-AppxPackage -Register AppxManifest.xml  
   {% endhighlight %}

![](/images/posts/powersh.png)

## Con esto ya disponemos de Android™

Ahora, solo basta con ir al a pestaña de inicio y abrir el **Windows Subsystem for Android™**. Quiero aclarar que las apps de google (Play Store, y algunas otras) **no aparecen instantaneamente** ya que se están **instalando en background**, por lo tanto, antes de venir a escribirme, ten paciencia... ya aparecerá todo. (Si aún no aparece la Play Store, reinicia).

<div class="gallery-box">
<div class="gallery">
<img src="/images/posts/android.png">
<img src="/images/posts/debbugin.png">
<img src="/images/posts/inicio.png">
</div>
</div>

## Ya podemos utilizar las apps de Google

Con estos simples pasos y este hermoso tutorial, ya podemos utilizar las apps de Google sin problemas.

![](/images/posts/playstore.png)

## Errores que pueden presentarse en la instalación

Es posible que no tengas habilitada la **virtualización**, o qué tal vez no sepas que es. Simplemente abre la **Powershell como Administrador** y escribe:

{% highlight bash %}  
_dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all_  
{% endhighlight %}

### Eso ha sido todo por hoy, luego haré otro tutorial explicando como instalar WSLg en 2 simples pasos. Por favor, si te gustó este post, te pido que me ayudes a divulgarlo. Y dejame un comentario, ¡así continuaré escribiendo post como este!