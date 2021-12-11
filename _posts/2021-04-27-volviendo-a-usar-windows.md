---
layout: post
title: Volviendo a usar WINDOWS
description: Cómo tengo configurado Windows, qué versión estoy usando, cómo configuré
  la terminal para utilizar WSL2.
date: 2021-04-27 03:00:00 +0000
image: "/images/posts/neofetch.png"
tags:
- Windows

---
Hacía muchísimo tiempo que no utilizaba Windows como mi Sistema Operativo personal. Lo he usado, obviamente para poder cumplir con algunas necesidades. Pero no mucho más que eso. Al dedicarme a compilar roms y trabajar bastante con el desarrollo de `Android` me es necesario trabajar con **Linux**. Sin embargo, he logrado suplir esa necesidad utilizando `WSL2`, junto con `Windows Terminal` y `VSCode`. A continuación voy a dejar algunos pasos de cómo tengo configurado todo y mis recomendaciones.

![](/images/posts/explorer.png)

## ¿Qué versión de Windows?

Esta es una de las decisiones más difíciles. Probé `Windows 10 Insider Preview [Build 21364]`, y está muy buena pero viene plagada de _bloatware_. Sin embargo, más adelante voy a tirar una solución que siempre utilizo.

Así que me quedaban dos opciones (dentro de lo que había elegido) MiniOS (de [Doofy Project](https://www.dprojects.org/minios)) y WinterOS (de [Marcos Cerqueiro](http://localhost:1313/posts/volviendo-a-usar-windows/Marcos%20Cerqueiro))

En resumen, MiniOS es una modificación de Windows 10, con lo es encial. No hay versiones LTSC y versiones completas 20H1. Cuenta con menú extendido que tiene un par de características “útiles”.

`WinterOS` es parecido. Cuenta con una versión LTSC y una `20H1`.

* Está muy bien **optimizado**.
* **Hay muchísima información** en sus videos de Youtube explica qué modificó, qué quitó y qué agregó. Lo cual es muy difícil de saber con respecto a MiniOS.
* El **menú extendido** tiene muchisimas herramientas útiles.
* Tiene una **guía** de qué hace cada sección y opción del menú.

![](/images/posts/stream.png)

Así que, como podrán notar, decidí utilizar la versión de `Marcos Cerqueiro (WinterOS)`.

## ¿Cómo lo he configurado?

Para la configuración hay una guía que el mismo autor deja en sus links (por lo tanto no voy a publicar acá dos veces lo mismo). Sin embargo, voy a dar mis tips o lo que yo he modificado.

### WinterOS Herramientas

Tengo deshabilitado todo. Windows Update, Windows Defender, Firewall, eliminado OneDrive por completo, y desactivado los servicios de impresión, Bluetooth y más.

### WinterOS Optimizadores Básicos

* `Streaming`. En esta opción solo configuré OBS-Studio. Ya que es mi principal herramienta para Streaming.
* `Producción`. Krita, Inkscape y Gimp.
* `Conexiones de Internet`. Acá seleciono las tres opciones.
* `Discos HDD y SDD/M.2 NVME`. Bueno, tengo los tres tipos de disco. Un disco HDD de 1tb, un SDD de 1tb y el NVME (donde tengo el SO) de 500gb.

### WinterOS Optimizadores “Gaming”

* `Optimizador de MODOS`.

![](/images/posts/modos.png)

En la opción de `modos`, tengo configurado en **GOLD**. Y he deshabilitado las otras opciones (Barra de juegos, HyperV, modo de juego de Windows)

* `Optimizador de CPU`

### Deshabilitando Servicios innecesarios

Esta parte no es sumamente necesaria, pero la verdad que funciona muy bien.

<iframe src="https://www.youtube.com/embed/AfmPNoIbJxI](https://youtu.be/AfmPNoIbJxI" frameborder="0" allowfullscreen></iframe>


Yo utilizo esta herramienta creada por EverythingTech. Dejo el link de [Descarga Directa](https://drive.google.com/drive/folders/1RYKqcqp6YzM0ZXArdWX70NWle6Q3BhYB). **Por favor, vean bien el video, sean precavidos y sigan la guía.**

### Mi Tema de Windows 10

Con mi tema de Windows, no me refiero a que sea mío, más bien el que yo decidí utilizar.

[![https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/i/d3c7a0fa-5f10-46fa-abe9-66c00454b216/ddnm3sf-53f9f344-3c56-42fb-afae-9bf99a0c5ae9.png](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/i/d3c7a0fa-5f10-46fa-abe9-66c00454b216/ddnm3sf-53f9f344-3c56-42fb-afae-9bf99a0c5ae9.png)

[Descárgalo desde aquí y sigue la guía del .zip](https://www.deviantart.com/kdr3w/art/Dev-825722799)

### Windows Terminal y VSCode

![](/images/posts/terminal.png)

# Daniell's dotfiles

!\[Visual Studio Code WSL: Ubuntu 20.04](https://i.imgur.com/ZBiFD0S.gif)

La configuración es muy sencilla, voy a dejar el link de [Github](https://github.com/daniellwdb/dotfiles) para que puedan descargar estos `Dotfiles`. Y configurarlo como yo lo hice.

La verdad, podría haber hecho un `Rice` desde cero y dejarlo todo como me gustaría, pero esta configuración me pareció muy útil.

# Bueno, eso es todo, creo que no tengo mucho más para agregar. A medida que pueda iré actualizando este post. Así que estén atentos todos los que gusten de usar Windows.
