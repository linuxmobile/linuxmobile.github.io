---
layout: post
title: Las mejores herramientas de Pen Testing para explorar con tu teléfono
description: 'Las mejores herramientas de Pen Tensting que se pueden encontrar en
  BlackArch para penetrar un móvil. '
date: 2020-08-25T03:00:00.000+00:00
image: https://images.unsplash.com/photo-1461749280684-dccba630e2f6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=869&q=80
tags:
- Seguridad
- Documentacion
- Android

---
## Intro

**Bueno, hoy tenía ganas de subir algo más sobre Pen Testing y seguridad informática. Explorando un poco la enorme cantidad de herramientas de** `BlackArch` **traté de elegir las mejores.**

## StaCoAn

`StaCoAn` es una herramienta multiplataforma que ayuda a desarrolladores, cazarrecompensas de errores y hackers a realizar análisis estáticos de aplicaciones móviles en el código de la aplicación para aplicaciones nativas de Android e iOS.

![](https://raw.githubusercontent.com/vincentcox/StaCoAn/master/resources/header_stacoan-01.png)

Esta herramienta buscará líneas en el código que pueden contener:

* Credenciales codificadas.
* Claves API.
* URL de API.
* Claves de Cifrado.
* Errores importantes en la codificación.

### Caracteristicas

El concepto de `StaCoAn` es muy sencillo, la “app” incluso te brinda una interfaz gráfica, y la posibilidad de arrastrar y soltar el .apk. Siendo de esta manera muy fácil de manejar el programa. Basta con iniciar a través de la **terminal** el programa, ir al navegador, arrastrar el .apk, soltarlo y ya estarías teniendo un breve analisis de la app.

**Los informes incluso contienen un práctico visor de árbol para que puedas navegar muy fácilmente a través de la app decompilada**

![](https://github.com/vincentcox/StaCoAn/raw/master/resources/mockup_screenshot.png)

### Instalar

**Por lo tanto para instalar solo basta con un simple comando**

{% highlight bash %}  
`sudo pacman -S stacoan`  
{% endhighlight %}

![](/images/posts/pacman.png)

**Para utilizarlo, exactamente como hicimos con** `Seeker`

{% highlight bash %}  
`./stacoan`  
{% endhighlight %}

## SigPloit

![](https://images.unsplash.com/photo-1563206767-5b18f218e8de?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=869&q=80)

`SigPloit` es una herramienta que te permite testear las señales **Telecom** y explorar las vulnerabilidades en los protocolos de señalización que utilizan los operadores móviles.

Algunas de las caracteristicas de `SigPloit` son:

* Seguimiento de localización.
* Interceptar SMS y llamadas.

**Para ver más sobre esta hermosa herramienta de Pen Testing les recomiendo seguir su** [Github](https://github.com/SigPloiter/SigPloit).

{% highlight bash %}

pacman -S sigploit

{% endhighlight %}

## rvi_capture (rvictl)

![](/images/posts/rvicapture.jpg)

`rvictl` es una herramienta excelente que sirve para capturar paquetes que entran y salen de dispositivos, tanto **Android como iOS.**

Esta herramienta puede ser un arma excelente para capturar todos los datos que se envían y reciben a través de la red, utilizada junto con `Wireshark`.

[rvictl](http://localhost:1313/posts/las-mejores-herramientas-de-pen-testing-para-explorar-con-tu-tel%C3%A9fono/rvictl)

## Quark

![](https://camo.githubusercontent.com/6bc95becd91a926ecaea0c89dcb2ca85e86d3070ab8a2d62254af3a23c9509df/68747470733a2f2f692e696d6775722e636f6d2f6e7a346d386b722e706e67.png)

**El concepto de** `Quark` **funciona como un motor de análisis de malware en Android.**

`Quark` desarrolló cinco etapas para comprobar si una app está practicando actividad maliciosa en el dispositivo.

1. Permisos solicitados.
2. Llamada de API nativa.
3. Combinaciones de la API nativa.
4. Secuencia de llamada de API nativa.
5. API que manejan el mismo registro.

**Para encontrar más info, como ya dije antes, dejo su link de** [**Github**](https://github.com/quark-engine/quark-engine)

Para instalar solo con el comando:

{% highlight bash %}

pacman -S quark

{% endhighlight %}

## Esto va a ser todo por hoy. Dentro de unos días voy a publicar la segunda parte de este mismo artículo. ¡No se lo pierdan y dejen su comentario, así me ayudan a crecer!
