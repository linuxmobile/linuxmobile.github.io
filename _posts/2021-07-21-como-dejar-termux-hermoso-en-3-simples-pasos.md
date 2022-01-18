---
layout: post
featured: false
title: "¡Cómo dejar Termux hermoso en 3 simples pasos!"
description: Termux, una de las mejores terminales para Android pero que luce un poco
  anticuada. Hoy te enseño como dejar Termux de la manera más linda posible!
date: 2021-07-21T03:00:00.000+00:00
image: https://mytermux-xshin404.vercel.app/assets/images/preview-3d60b7d9d08bcef67420fd52af4c1846.png
tags:
- Android
- Termux

---
## Intro

`Termux` es un emulador de terminal disponible para **Android, de manera gratuita y OpenSource**. Cuenta con una **comunidad** [**enorme**](http://localhost:1313/posts/como-dejar-termux-hermoso-en-3-simples-pasos/enorme) dentro del mundo de Android y Linux. En la cual se puede encontrar muchísima información útil.

Con `Termux` se pueden hacer miles de cosas.

# Instalar Arch

![](/images/posts/termuxarch.jpg)

# Instalar herramientas de hacking ético

<div class="gallery-box">
<div class="gallery">
<img src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/toolx.png">
<img src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/toolx_cat.png">
<img src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/Screenshot_2020-05-17-20-17-56.png">
</div>
</div>

# Y también customizarlo

![](https://mytermux-xshin404.vercel.app/assets/images/preview-3d60b7d9d08bcef67420fd52af4c1846.png)

***

# Instalando Termux

La aplicación de `Termux` la podemos encontrar fácilmente en [F-Droid](http://localhost:1313/posts/como-dejar-termux-hermoso-en-3-simples-pasos/F-Droid). La versión de la _Play Store está obsoleta, y en Github, Termux recomienda no instalar en lo absoluto la versión de allí._ Por lo tanto lo mejor es bajar el **APK** desde F-Droid.

Una vez instalada la aplicación, la abrimos y escribimos:

{% highlight html %}  
termux-setup-storage  
{% endhighlight %}

Eso es para darle a `Termux` los permisos para acceder a nuestro Storage.

## Instalando los Dotfiles

Para dejar `Termux` bellísimo. Vamos a utilizar los **Dotfiles** de [xshin404](http://localhost:1313/posts/como-dejar-termux-hermoso-en-3-simples-pasos/xshin404)

Así que vamos a ello.

{% highlight html %}  
pkg update && pkg upgrade # Para actualizar termux y sus paquetes  
{% endhighlight %}

{% highlight html %}  
pkg install ncurses-utils bc git  
{% endhighlight %}

{% highlight html %}  
git clone [https://github.com/xshin404/myTermux](https://github.com/xshin404/myTermux "https://github.com/xshin404/myTermux")  
{% endhighlight %}

{% highlight html %}  
cd myTermux  
{% endhighlight %}

{% highlight html %}  
cp .xshin.var $HOME  
{% endhighlight %}

{% highlight html %}  
chmod +x install.sh # le damos los permisos de ejecución  
{% endhighlight %}

Para correr el script hay dos opciones **Full y Lightweight.** Para conocerlas basta con ejecutar `./install.sh help`

{% highlight html %}  
./install \[options\] # Hay dos opciones Full y Lightweight  
{% endhighlight %}

Una vez hayamos instalado todo quedan los pasos finales:

{% highlight html %}  
nvim  
\# Una vez dentro de neovim instalamos los plugins  
:PackerInstall  
{% endhighlight %}

## Comentarios finales

Eso es todo. Voy a dejar algunos comandos que son útiles y que disponemos ahora que ya hemos instalado los Dotfiles.

{% highlight html %}  
cava    # Visualizer  
ncmpcpp # Reproductor de música local  
nvim    # Editor de texto  
chcolor # Para cambiar los colores  
chfont  # Para cambias la fuente tipográfica  
neo     # Neofetch fachero  
ls      # En vez del natural ls, utilizamos 'exa'  
{% endhighlight %}

# Espero que les haya gustado este post. Me ayudarían muchísimo comentando y compartiendo este post en donde sea: Grupos de Telegram, Redes Sociales, ustedes saben.-

_Para poder ver algunos ajustes, como la batería, en Neofetch vamos a necesitar Termux-Api (también lo encontramos en F-Droid y además de instalarlo como apk, debemos instalarlo con `pkg install termux-api`)_