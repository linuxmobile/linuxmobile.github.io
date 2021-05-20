---
weight: 1
title: "Silicon, una bella herramienta para mostrar tu código"
date: 2021-05-20
lastmod: 2021-05-20
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Sílicon una herramienta para mostrar código al mejor estilo carbon"
resources:
- name: "featured-image"
  src: "silicon.png"

tags: ["linux", "terminal", "herramientas"]
categories: ["terminal", "documentacion"]

lightgallery: false

toc:
  auto: false
---

Seguramente ya conocen la herramienta online `carbon`. Un excelente accesorio para mostrar tu código. Hoy vamos a explorar y conocer `Silicon`. 

<!--more-->

## Intro

Para entrar más en detalle `carbon` es una herramienta muy útil, bella y creativa que te ayuda a mostrar el código que hayas escrito o que quieras mostrar. Esto te puedo asegurar que lo viste miles de veces en post de `Twitter` y/o `Instagram`

{{< image src="https://user-images.githubusercontent.com/8397708/63456416-b27d1a80-c403-11e9-9572-105b089be885.png" >}}

Pero esta herramienta solo está disponible online. Por lo tanto tiene algunas desventajas. 
- No puede trabajar sin internet.
- Y no funciona bien con shell. 

`Silicon` no tiene esos problemas. Funciona sin necesidad de estar conectados a internet. Está escrito en `Rust`. La desventaja, **que ellos mismos te lo explican** no es tan bello como `carbon`.

## Instalando Silicon

# Arch (AUR)

```bash
yay -S silicon
```

# Cargo

```bash
cargo install silicon
```

# Dependencias

**Arch**
```bash
sudo pacman -S --needed pkgconf freetype2 fontconfig libxcb xclip
```
**Ubuntu**
```bash
sudo apt install expat
sudo apt install libxml2-dev
sudo apt install pkg-config libasound2-dev libssl-dev cmake libfreetype6-dev libexpat1-dev libxcb-composite0-dev
```
**Fedora**
```bash
sudo dnf install cmake expat-devel libxcb-devel freetype-devel libxml2-devel
```

## Usando silicon

Desde un archivo
```bash
silicon main.js -o main.png 
```

Desde el clipboard
```bash
silicon --from-clipboard -l .xml --to-clipboard
```


Bueno, el post podría tener mucho más explicaciones pero creo que lo mejor es ir a  {{< link="https://github.com/Aloxaf/silicon" "github">}} y analizar todo ustedes mismos. 

# Espero que les sea muy útil esta herramienta, y pronto se vienen algunos tutoriales más interesantes. 
