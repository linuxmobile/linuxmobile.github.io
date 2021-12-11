---
layout: post
title: Instalando Arch-WSL2 en Windows 2021 - 2da Parte
description: Hoy vamos a aprender, juntos, a instalar ArchLinux dentro de Windows,
  aprovechando la herramienta del subsistema de Linux.
date: 2021-03-31T03:00:00.000+00:00
image: https://i2.wp.com/mundowin.com/wp-content/uploads/2020/02/WIndows-Linux.png?w=832&ssl=1
tags:
- Windows
- Linux
- Documentacion

---
## Intro

Para estas instancias del tutorial ya deberías haber instalado `WSL2`. Si aún no lo has hecho, te recomiendo que veas nuestro post anterior.

## Instalando Arch en WSL2

![](https://raw.githubusercontent.com/wiki/yuk7/wsldl/img/Arch_Alpine_Ubuntu.png)

Si seguiste todo al pie de la letra, **no deberías tener mayores complicaciones al instalar** `Arch` dentro de Winbugs.

1. Descargamos lo necesario [`desde aquí`](https://github.com/yuk7/ArchWSL/releases/latest)

![](/images/posts/release.png)

1. En el link vamos a encontrar tres archivos diferentes. Uno es un `.Appx`, otro es un `.cer` y un `.zip`. _Solo vamos a necesitar el .appx y .cer_
2. Una vez hayamos descargado debemos instalar el archivo `.cer` de manera manual.

<div class="gallery-box">
<div class="gallery">
<img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/1.install.png">
<img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/2.to-localmachine.png">
<img src="https://wsldl-pg.github.io/ArchW-docs/img/cert/4.to-trustedpeople.png">
</div>
</div>

Luego de haber instalado el certificado correctamente, vamos a instalar el `.appx`. Una forma sencilla de hacerlo es con doble click e instalan. Pero en caso de que (como yo) tengan algún inconveniente de instalar corren este comando en la _shell_, y se les instala sin problemas. (Recuerden que para tirar el comando deben abrir Powershell en la carpeta donde tienen descargado el `.appx`)

{% highlight bash %}
Add-AppxPackage ArchWSL-AppX_20.11.25.0_x64.appx
{% endhighlight %}

    En el caso de que tengamos un error similar a este: HRESULT:0x80370102, abrimos Powershell (siempre como administrador) y ejecutamos bcdedit /set hypervisorlaunchtype auto start y reiniciamos.

## Configurando Arch

_Si todo salió bien luego de la instalación les aparecerá el ícono de Arch para poder correr el subsistema. Entonces corriendo Arch, vamos a ejecutar estos comandos para poder configurarlo._

1. Configuramos el Usuario y Contraseña

{% highlight bash %}
\# Configuras tu contraseña root
passwd
\# Configuras el archivo sudoers
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
\# Añades tu usuario
useradd -m -G wheel -s /bin/bash yourusername
\# Configuras la contraseña de tu usuario
passwd yourusername
{% endhighlight %}

Y cierras.

2. Abres nuevamente la Powershell (como administrador) y escribes:

{% highlight bash %}
Arch.exe config --default-user yourusername
{% endhighlight %}

## Configurando arch desde dentro

_Bien, ya tienes configurado Arch para poder utilizarlo, pero debemos configurarlo para que pueda ser usado tal y como es._

1. Iniciamos los _keyrings_ (necesario para poder correr pacman).

{% highlight bash %}
sudo pacman-key --init && sudo pacman-key --populate
{% endhighlight %}

2. Actualizamos pacman e instalamos algunas utilidades.

{% highlight bash %}
sudo pacman -Syy && sudo pacman -Syu
{% endhighlight %}

3. Habilitamos multilib

{% highlight bash %}
linenumber=$(grep -nr "\\\\#\\\\\[multilib\\\\\]" /etc/pacman.conf | gawk '{print $1}' FS=":")
sed -i "${linenumber}s:.*:\[multilib\]:" /etc/pacman.conf
linenumber=$((linenumber+1))
sed -i "${linenumber}s:.*:Include = /etc/pacman.d/mirrorlist:" /etc/pacman.conf
\# actualizamos nuevamente
pacman -Syy
{% endhighlight %}

{% highlight bash %}
\# Instalamos y actualizamos algunos paquetes necesarios
sudo pacman -S base base-devel git nano wget reflector
{% endhighlight %}

4. Actualizamos los mirrors con reflector

{% highlight bash %}
reflector --verbose --latest 5 --sort rate --save /etc/pacman.d/mirrorlist
{% endhighlight %}

## Instalamos yay

{% highlight bash %}
mkdir \~/yay && cd \~/yay

wget "[https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=yay](https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=yay "https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=yay")" --output-document=./PKGBUILD

makepkg -si
{% endhighlight %}

## Listo!

_Ahora con Arch instalado dentro de Windows, podremos hacer cuanto quisiéramos. Luego, más adelante, realizaré otro tutorial, enseñando a instalar ohmyzsh y algunos plugins interesantes para esta hermosa herramienta._

# No se pierdan nuestro próximo post y si tuvieron algún problema, ¡¡¡no duden en escribirnos en los comentarios!!!
