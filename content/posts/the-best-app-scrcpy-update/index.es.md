---
weight: 1
title: "La mejor app para compartir pantalla 'Scrcpy' se actualiza"
date: 2020-08-09
lastmod: 2020-08-09
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Ya está disponible una nueva versión de Scrcpy, la manera más fácil de de compartir la pantalla de tu Android e interactuar con él.."
resources:
- name: "featured-image"
  src: "scrot-running.png"

tags: ["android", "app"]
categories: ["android"]

lightgallery: true

toc:
  auto: false
---

Ya está disponible una nueva versión de Scrcpy, la manera más fácil de de compartir la pantalla de tu Android e interactuar con él

<!--more-->


## 1 Intro {#intro}


Una nueva versión de {{< link "https://github.com/Genymobile/scrcpy" Scrcpy "Prueba Scrcpy!" >}}, la excelente herramienta para compartir la pantalla de tu Android en el PC, ya está disponible.


## 2 Novedades {#novedades}

Scrcpy v1.15 ahora proporciona la habilidad de utilizar atajos de teclado como `Ctrl` y `Shift` en el teléfono. Esto significa que ahora puedes utilizar los atajos de teclado familiares como copiar y pegar en `termux`, `Ctrl + t` para abrir una nueva ventana en tu navegador preferido o simplemente algo tan comodo como `Shift + →` para seleccionar texto.

{{< image src="scrot-wireless.png" caption="`Scrot corriendo con wifi`" >}}

Además de la tecla `Ctrl` **Scrcpy** también puede utilizar `Alt Izq`, `AltGr` y `Super` (la tecla de windows o command). _Claro que esta opción puede ser modificada o desactivada si no te gusta_.

Copiar y pegar también se ha mejorado enormemente en esta versión, basándose en la sincronización automática del portapapeles de la última versión presentada. Además de ser más fácil de usar, **el tamaño del portapapeles se ha incrementado a 256k** (en comparación con solo 4k).

## 3 Descarga

Scrcpy es una herramienta gratuita de código abierto que está disponible para Windows, macOS y Linux. Puedes, como siempre, obtener la última versión de la página del proyecto **{{< link "https://github.com/Genymobile/scrcpy" Github "Prueba Scrcpy!" >}}**.

### Instalación en Arch

Si eres un usuario de `Arch Linux` puedes utilizar este comando para instalar y probar esta hermosa herramienta:

```Shell
yay -S scrcpy
```
{{< image src="install.png" caption="`Instalar scrcpy es fácil y sencillo`" >}}
