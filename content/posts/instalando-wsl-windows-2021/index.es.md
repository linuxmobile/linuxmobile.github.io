---
weight: 1
title: "Instalando Arch-WSL2 en Windows 2021"
date: 2021-03-27
lastmod: 2021-03-27
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Hoy vamos a instalar Archlinux dentro de Windows, con la ayuda de wsl2."
resources:
- name: "featured-image"
  src: "wsl2.jpeg"

tags: ["linux", "wsl2", "windows", "arch"]
categories: ["linux", "documentation"]

lightgallery: false

toc:
  auto: false
---

Hoy vamos a aprender, juntos, a instalar Archlinux dentro de Windows, aprovechando la herramienta del subsistema de linux.

<!--more-->

{{< admonition type=tip title="**INFO**" open=true >}}En este tutorial, vamos a aprender como instalar wsl2, y además Archlinux (lo cual no es compatible de forma nativa con Windows).
{{< /admonition >}}


## Intro


¡Primero lo primero! **WSL2 (Windows Subsystem for Linux Version 2)** es la nueva arquitectura que permite ejecutar `Linux` dentro de Windows 10 de manera nativa. Y está destinada a reemplazar WSL1.

Esta nueva versión ejecuta el kernel de `Linux` en tiempo real. Lo cual mejora el rendimiento y compatibilidad de las aplicaciones y paquetes respecto a la versión anterior.



## Preparando Windows

Para poder instalar cualquier wsl, ya sea el wsl1 tanto como el wsl2 debemos habilitar dos opciones que se encuentran dentro de las caracteristicas de windows. 

**Para poder instalar estas opciones debemos ir a**
1. **Inicio** de Windows
2. **Activar o Desactivar caracteristicas de Windows** (usa el cuadro de busquedas)
3. Habilitamos **Plataforma de máquina virtual** y **Subsistema de Windows para Linux**

{{< image src="https://i3g4v6w8.stackpathcdn.com/wp-content/uploads/2019/06/enable-wsl1-windows-10.jpg" caption="Aquí un ejemplo." >}}

4. Aceptar
5. Reinician!

## Habilitar la Máquina Virtual
{{< admonition type=warning title="ATENCIÓN" open=true >}}
La `motherboard` y el procesador deben admitir la virtualización, y la opción `debe estar habilitada` en el sistema básico de entrada/salida (BIOS) o en la interfaz de firmware extensible unificada (UEFI).
{{< /admonition >}}

1. **Click derecho en inicio**
2. **Windows Powershell (administrador)**
3. Escribimos en la powershell.
```shell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform
```
4. Reiniciamos

{{< admonition type=tip title="Atención" open=false >}}
Hasta este punto, ya tenemos instalado y habilitado WSL. Pero continuaremos hasta habilitar WSL2
{{< /admonition >}}

## Activando WSL2 

Para poder convertir `wsl1` en `wsl2` tienen que seguir estos pasos:

1. Descargan e instalan el kernel `{{< link "https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi" WSL2 >}}`  **(obligatorio)**
2. Una vez instalado abren otra vez la powershell (administrador)
3. 
```shell
wsl --set-default-version 2
```

## Instalando Arch en WSL2

{{< image src="https://raw.githubusercontent.com/wiki/yuk7/wsldl/img/Arch_Alpine_Ubuntu.png" caption="Archlinux corriendo en windows" >}}

Para no alargar demasiado el tutorial. Quisiera aclarar que ya no es necesario continuar con esto, si solamente quisieras una versión de linux que corra de forma nativa
te voy a dejar unos enlaces que simplemente instalas ejecutando.

`{{< link "https://aka.ms/wslubuntu2004" "Ubuntu 20.04" >}}`

`{{< link "https://aka.ms/wsl-ubuntu-1804" "Ubuntu 18.04" >}}`

`{{< link "https://aka.ms/wsl-ubuntu-1604" "Ubuntu 16.04" >}}`

`{{< link "https://aka.ms/wsl-debian-gnulinux" "Debian GNU/Linux" >}}`

`{{< link "https://aka.ms/wsl-kali-linux-new" "Kali Linux" >}}`

`{{< link "https://aka.ms/wsl-opensuse-42" "OpenSuse Leap 42" >}}`

`{{< link "https://github.com/WhitewaterFoundry/WSLFedoraRemix/releases/" "Fedora Remix" >}}`



# Si te interesa continuar con el tutorial e instalar Archlinux dentro de WSL2, continúa con la segunda parte.
