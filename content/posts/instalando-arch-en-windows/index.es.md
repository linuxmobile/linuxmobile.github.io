---
weight: 1
title: "Instalando Arch-WSL2 en Windows 2021 - 2da Parte"
date: 2021-03-31
lastmod: 2021-03-31
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

{{< admonition type=tip title="**INFO**" open=true >}}En este tutorial, vamos a aprender como instalar Archlinux dentro de Windows con WSL2 (lo cual no es soportado de forma nativa con Windows).
{{< /admonition >}}


## Intro


Para estas instancias del tutorial, ya deberías haber instalado `WSL2`. Si aún no lo has hecho te recomiendo que veas nuestro post anterior.


## Instalando Arch en WSL2

{{< image src="https://raw.githubusercontent.com/wiki/yuk7/wsldl/img/Arch_Alpine_Ubuntu.png" caption="archwsl." >}}


Si seguiste todo al pie de la letra, **no debería tener mayores complicaciones instalar** `Arch` dentro de windows.

1. Descargamos lo necesario `{{< link "https://github.com/yuk7/ArchWSL/releases/latest" "desde aquí">}}`

{{< image src="release.png">}}

2. En el link vamos a encontrar tres archivos diferentes. Uno es un `.Appx`, otro es un `.cer` y un `.zip`.
_Solo vamos a necesitar el .appx y .cer_
3. Una vez hayamos descargado debemos instalar el archivo `.cer` de manera manual. 

{{< image src="https://wsldl-pg.github.io/ArchW-docs/img/cert/1.install.png">}}
{{< image src="https://wsldl-pg.github.io/ArchW-docs/img/cert/2.to-localmachine.png">}}
{{< image src="https://wsldl-pg.github.io/ArchW-docs/img/cert/3.to-following.png">}}
{{< image src="https://wsldl-pg.github.io/ArchW-docs/img/cert/4.to-rootstore.png">}}

4. Luego de haber instalado el certificado correctamente, vamos a instalar el `.appx`. 
Una forma sencilla de hacerlo es con doble click e instalan. Pero en caso de que (como yo) tengan algún inconveniente de instalar 
corren este comando en la shell, y se les instala sin problemas. (Recuerden que para tirar el comando deben abrir powershell en la carpeta donde tienen descargado el `.appx`)
```powershell
Add-AppxPackage ArchWSL-AppX_20.11.25.0_x64.appx
```

## Configurando Arch

_Sí todo salió bien luego de la instalación les aparecerá el ícono de Arch para poder correr el subsistema. Entonces corriendo arch, vamos a ejecutar estos comandos para poder configurarlo._

1. Configuramos el Usuario y Contraseña

```powershell
# Configuras tu contraseña root
passwd
# Configuras el archivo sudoers
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
# Añades tu usuario
useradd -m -G wheel -s /bin/bash yourusername
# Configuras la contraseña de tu usuario
passwd yourusername
```
Y cierras.

2. Abres nuevamente la powershell y escribes:
```powershell
Arch.exe config --default-user yourusername
```


## Configurando arch desde dentro
_Bien, ya tienes configurado arch para poder utilizarlo, pero debemos configurar arch para que pueda ser usado tal y como es_

1. Iniciamos los keyrings (necesario para poder correr pacman)
```powershell
sudo pacman-key --init && sudo pacman-key --populate
```

2. Actualizamos pacman e instalamos algunas utilidades.
```powershell
sudo pacman -Syy && sudo pacman -S base base-devel git nano wget reflector
```

3. Habilitamos multilib 
```powershell
linenumber=$(grep -nr "\\#\\[multilib\\]" /etc/pacman.conf | gawk '{print $1}' FS=":")
sed -i "${linenumber}s:.*:[multilib]:" /etc/pacman.conf
linenumber=$((linenumber+1))
sed -i "${linenumber}s:.*:Include = /etc/pacman.d/mirrorlist:" /etc/pacman.conf

# actualizamos nuevamente
pacman -Syy
```

4. Actualizamos los mirrors con reflector
```powershell
reflector --verbose --latest 5 --sort rate --save /etc/pacman.d/mirrorlist
```


## Instalamos yay
```powershell
mkdir ~/yay && cd ~/yay
wget "https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=yay" --output-document=./PKGBUILD
makepkg -si
```


## Listo!

_Ahora con Arch instalado dentro de windows, podremos hacer cuanto quisieramos. Luego más adelante realizaré otro tutorial, enseñando a instalar ohmyzsh y algunos plugins interesantes para esta hermosa herramienta._

# No se pierdan nuestro próximo post, y si tuvieron algún problema, no duden en escribirnos en los comentarios!!!
