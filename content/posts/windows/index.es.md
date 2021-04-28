---
weight: 1
title: "Volviendo a usar WINDOWS"
date: 2021-04-27
lastmod: 2021-04-27
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "He vuelto a usar Windows como mi Sistema Operativo Único."
resources:
- name: "featured-image"
  src: "neofetch.png"

tags: ["windows", "terminal", "sistemas operativos"]
categories: ["windows"]

lightgallery: false

toc:
  auto: false
---

Cómo tengo configurado Windows, qué versión estoy usando, cómo configuré la terminal para utilizar WSL2. 

<!--more-->
{{< admonition type=alert title="**ALERT**" open=true >}} Una no breve introducción.
{{< /admonition >}}

Hacía muchísimo tiempo que no utilizaba Windows como mi Sistema Operativo Personal. Lo he usado, obviamente para poder cumplir con algunas necesidades. Pero no mucho más que eso.
Al dedicarme a compilar roms y trabajar bastante con el desarrollo de `Android` me es necesario trabajar con **Linux**. Sin embargo, he logrado suplir esa necesidad utilizando `WSL2`, junto con `Windows Terminal` y `VSCode`. A continuación voy a dejar algunos pasos de cómo tengo configurado todo y mis recomendaciones.

{{< image src="explorer.png" caption="Un vistazo a mi Windows 10" >}}

## Qué versión de Windows?

Esta es una de las deciciones más dificiles. Probé `Windows 10 Insider Preview [Build 21364]`, y está muy buena pero viene plagada de bloatware. Sin embargo más adelante voy a tirar una solución que siempre utilizo.

Así que me quedaban dos opciones (dentro de lo que había elegido) MiniOS (de {{<link "https://www.dprojects.org/minios" "Doofy Project">}}) y WinterOS  (de {{<link="https://www.youtube.com/watch?v=jPDNasAukCo&t=416s" "Marcos Cerqueiro" >}})

En resumen, MiniOS es una modificación de Windows 10, con lo escencial. No hay versiones LTSC y versiones completas 20H1. Cuenta con menú extendido que tiene un par de características "útiles".

`WinterOS` es parecido. Cuenta con una versión LTSC y una `20H1`.
 - Está muy bien **optimizado**.
 - **Hay muchísima información** en sus videos de Youtube donde explica qué modificó, qué quitó y qué agregó. Lo cual es muy difícil de saber con respecto a MiniOS. 
 - El **menú extendido** tiene muchisimas herramientas útiles.
 - Tiene una **guía** de qué hace cada sección y opción del menú.

{{< image src="stream.png" >}}

Así que como podrán notar, decidí utilizar la versión de `Marcos Cerqueiro (WinterOS)`. 


##  Cómo lo he configurado?

Para la configuración hay una guía que el mismo autor deja en sus links (por lo tanto no voy a publicar acá dos veces lo mismo.) Sin embargo, voy a dar mis tips o lo que yo he modificado.

### WinterOS Herramientas

Tengo deshabilitado todo. Windows Update, Windows Defender, Firewall, eliminado OneDrive por completo, y desactivado los servicios de impresión, Bluetooth y más. 

### WinterOS Optimizadores Básicos

- `Streaming`. En esta opción solo configuré OBS-Studio. Ya que es mi principal herramienta para Streaming.
- `Producción`. Krita, Inkscape y Gimp. 
- `Conexiones de Internet`. Acá seleciono las tres opciones.
- `Discos HDD y SDD/M.2 NVME`. Bueno, tengo los tres tipos de disco. Un disco HDD de 1tb, un SDD de 1tb y el NVME (donde tengo el SO) de 500gb.

### WinterOS Optimizadores "Gaming"

- `Optimizador de MODOS`. 

{{< image src="modos.png" >}}

En la opción de `modos`, tengo configurado en **GOLD**. Y he deshabilitado las otras opciones (Barra de juegos, HyperV, modo de juego de Windows)
- `Optiizador de CPU`

### Deshabilitando Servicios Innecesarios

Esta parte no es sumamente necesaria, pero la verdad que funciona muy bien. 

{{< youtube AfmPNoIbJxI >}}

Yo utilizo esta herramienta creada por EverythingTech. Dejo el link de {{< link "https://drive.google.com/drive/folders/1RYKqcqp6YzM0ZXArdWX70NWle6Q3BhYB" "Descarga Directa" >}}. **Por favor, vean bien el video, sean precavidos y sigan la guía.**

### Mi Tema de Windows 10

Con mi tema de Windows, no me refiero a que sea mío, más bien a el que yo decidí utilizar. 

{{< image src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/i/d3c7a0fa-5f10-46fa-abe9-66c00454b216/ddnm3sf-53f9f344-3c56-42fb-afae-9bf99a0c5ae9.png" >}}

{{< link "https://www.deviantart.com/kdr3w/art/Dev-825722799" "Descargalo desde aquí y sigue la guía del .zip" >}}

### Windows Terminal y VSCode

{{< image src="terminal.png" >}}


{{< admonition type=tip title="**TIP**" open=true >}} Si todavía no conoces o no tenés instalada la Terminal de Windows, te dejo un link para {{< link "https://github.com/microsoft/terminal/releases/latest" "descargar">}}
{{< /admonition >}}


<div align="center">
  <h1>Daniell's dotfiles</h1>
  <img src="https://i.imgur.com/ZBiFD0S.gif" width="980px" alt="Visual Studio Code (WSL: Ubuntu 20.04)">
</div>

La configuración es muy sencilla, voy a dejar el link de {{< link "https://github.com/daniellwdb/dotfiles" "Github" >}} para que puedan descargar estos `Dotfiles`. Y configurarlo como yo lo hice. 

La verdad, podría haber hecho un `Rice` desde cero, y dejarlo todo como me gustaría, pero esta configuración me pareció muy útil. 


# Bueno, eso es todo, creo que no tengo mucho más para agregar. A medida que pueda iré actualizando este post. Así que estén atentos todos los que gusten de usar Windows.
