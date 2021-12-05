---
layout: post
title: Instalando Arch-WSL2 en Windows 2021 - 2da Parte
description: Hoy vamos a aprender, juntos, a instalar Archlinux dentro de Windows,
  aprovechando la herramienta del subsistema de linux.
date: 2021-03-31 03:00:00 +0000
image: https://i2.wp.com/mundowin.com/wp-content/uploads/2020/02/WIndows-Linux.png?w=832&ssl=1
tags:
- Windows
- Linux
- Documentacion

---
## Intro

Para estas instancias del tutorial, ya deberías haber instalado `WSL2`. Si aún no lo has hecho te recomiendo que veas nuestro post anterior.

## Instalando Arch en WSL2

![](https://raw.githubusercontent.com/wiki/yuk7/wsldl/img/Arch_Alpine_Ubuntu.png)

Si seguiste todo al pie de la letra, **no debería tener mayores complicaciones instalar** `Arch` dentro de windows.

1. Descargamos lo necesario [`desde aquí`](https://github.com/yuk7/ArchWSL/releases/latest)

![](/uploads/release.png)

2. En el link vamos a encontrar tres archivos diferentes. Uno es un `.Appx`, otro es un `.cer` y un `.zip`. _Solo vamos a necesitar el .appx y .cer_
3. Una vez hayamos descargado debemos instalar el archivo `.cer` de manera manual.

  <div class="gallery-box">
    <div class="gallery">
      <img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/1.install.png">
      <img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/2.to-localmachine.png">
      <img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/4.to-trustedpeople.png">
    </div>
  </div>
  