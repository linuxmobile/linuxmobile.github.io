---
layout: post
featured: false
title: "Configurando VSCODE en archlinux"
description: Hoy vamos a configurar vscode en archlinux de la mejor manera posible. Nos preparamos para el siguiente post!
date: 2022-02-06
image: https://i.imgur.com/mICQnlG.png
tags:
- Documentacion
- Linux
---

### Introducción 

_Hoy les quiero enseñar como instalar [VSCODE](https://github.com/microsoft/vscode) de la manera más sencilla posible. Y además como configurarlo para que quede increíble._

### Instalando VSCODE

_Para instalar voy a utilizar [Paru](https://github.com/Morganamilo/paru) como mi AUR Helper. ¡Podés utilizar cualquier otro!_

{% highlight bash %}
paru -S code code-features code-marketplace
{% endhighlight %}

#### Instalamos Cascadia Code NF (opcional)

_Esto es absolutamente opcional. Pero lo cierto es que quedan muy bien con VSCODE._ 

{% highlight shell %}
# Creamos la carpeta nerdfonts
mkdir -p $HOME/Downloads/nerdfonts/
cd $HOME/Downloads/
# Descargamos la fuente 
wget https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/CascadiaCode.zip
# La descomprimimos dentro de la carpeta nerdfonts 
unzip '*.zip' -d $HOME/Downloads/nerdfonts/
# Borramos el .zip 
rm -rf *.zip
# Y con sudo, lo copiamos a la carpeta "fonts" del sistema.
sudo cp -R $HOME/Downloads/nerdfonts/ /usr/share/fonts/
{% endhighlight %}

