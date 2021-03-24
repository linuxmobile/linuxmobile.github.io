---
weight: 1
title: "Las mejores herramientas de Pen Testing para explorar con tu teléfono"
date: 2020-08-25T10:11:00
lastmod: 2020-08-25
draft: draft
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Las mejores herramientas de Pen Tensting que se pueden encontrar en BlackArch para penetrar un móvil."
resources:
- name: "featured-image"
  src: "tools.jpg"

tags: ["tools", "android", "herramientas"]
categories: ["android", "documentation", "seguridad"]

lightgallery: true

toc:
  auto: false
---
<h1>Parte 1</h1>
Las mejores herramientas de Pen Tensting que se pueden encontrar en BlackArch para penetrar un móvil.


<!--more-->



## Intro

**Bueno, hoy tenía ganas de subir algo más sobre Pen Testing y seguridad informática. Explorando un poco la enorme cantidad de herramientas de** `BlackArch` **traté de elegir las mejores.**

## StaCoAn {#stacoan} 

`StaCoAn` es una herramienta multiplataforma que ayuda a desarrolladores, cazarrecompensas de errores y hackers a realizar
análisis estáticos de aplicaciones móviles en el código de la aplicación para aplicaciones nativas de Android e iOS.

{{< image src="header.png" >}}

Esta herramienta buscará líneas en el código que pueden contener:
* Credenciales codificadas.
* Claves API.
* URL de API.
* Claves de Cifrado.
* Errores importantes en la codificación.


### Caracteristicas

El concepto de `StaCoAn` es muy sencillo, la "app" incluso te brinda una interfaz gráfica, y la posibilidad de arrastrar y soltar el .apk. Siendo de esta manera muy fácil de manejar el programa.
Basta con iniciar a través de la **terminal** el programa, ir al navegador, arrastrar el .apk, soltarlo y ya estarías teniendo un breve analisis de la app.

**Los informes incluso contienen un práctico visor de árbol para que puedas navegar muy fácilmente a través de la app decompilada**

{{< image src="tree.png" >}}

*El listado completo de caracteristicas se puede encontrar muy fácil en su repositorio de {{< link "https://github.com/vincentcox/StaCoAn#features" Github >}}*

### Instalar {#instalar}

**En nuestro post {{< link "https://linuxmobile.github.io/posts/seeker.-una-herramienta-para-obtener-datos-de-geolocalización/" Seeker >}} explicamos como acceder a los repositorios de** `BlackArch`.

{{< image src="post.png" caption="Seeker. Una herramienta para obtener datos de Geolocalización " >}}

**Por lo tanto para instalar solo basta con un simple comando**

```zsh
sudo pacman -S stacoan
```

{{< image src="pacman.png" >}}


**Para utilizarlo, exactamente como hicimos con** `Seeker`

```zsh
./stacoan
```

## SigPloit {#SigPloit}

{{< image src="exploit.jpg" >}}

`SigPloit` es una herramienta que te permite testear las señales **Telecom** y explorar las vulnerabilidades in los protocolos de señalización que utilizan los operadores móviles.

Algunas de las caracteristicas de `SigPloit` son:

* Seguimiento de localización.
* Interceptar SMS y llamadas.

**Para ver más sobre esta hermosa herramienta de Pen Testing les recomiendo seguir su** {{< link "https://github.com/SigPloiter/SigPloit" Github >}}.

```zsh
pacman -S sigploit
```

## rvi_capture (rvictl) {#rvi_capture}

{{< image src="rvicapture.jpg" >}}

`rvictl` es una herramienta excelente que sirve para capturar paquetes que entran y salen de dispositivos, tanto **Android como iOS.**

Esta herramienta puede ser un arma excelente para capturar todos los datos que se envían y reciben a través de la red, utilizada junto con `Wireshark`.

{{< link="https://github.com/gh2o/rvi_capture" rvictl >}}


## Quark {#quark}

{{< image src="quark.png" >}}

**El concepto de** `Quark` **funciona como un motor de análisis de malware en Android.** 

`Quark` desarrolló cinco etapas para comprobar si una app está practicando actividad maliciosa en el dispositivo.

1. Permisos solicitados.
2. Llamada de API nativa.
3. Combinaciones de la API nativa.
4. Secuencia de llamada de API nativa.
5. API que manejan el mismo registro.

**_Les dejo un breve video de como funciona._**

[![asciicast](https://asciinema.org/a/292752.svg)](https://asciinema.org/a/292752)


**Para encontrar más info, como ya dije antes, dejo su link de {{< link "https://github.com/quark-engine/quark-engine" Github >}}**

Para instalar solo con el comando:
```zsh
pacman -S quark
```
---

<h2>Esto va a ser todo por hoy. Dentro de unos días voy a publicar la segunda parte de este mismo artículo. No se lo pierdan y dejen su comentario, así me ayudan a crecer!</h2>

