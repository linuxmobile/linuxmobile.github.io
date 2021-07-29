---
weight: 1
title: "Como dejar Termux hermoso en 3 simples pasos!"
date: 2021-07-29
lastmod: 2021-07-29
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Como dejar Termux de una manera hermosa"
resources:
- name: "featured-image"
  src: "vimplug.png"

tags: ["termux", "terminal", "dotfiles", "android"]
categories: ["termux","android"]

lightgallery: true

toc:
  auto: false
---

Termux, una de las mejores terminales para Android pero que luce un poco anticuada. Hoy te enseño como dejar `Termux` de la manera más linda posible!

<!--more-->

## Intro

`Termux` es un emulador de terminal disponible para **Android, de manera gratuita y opensource**. Cuenta con una **comunidad {{< link="https://github.com/termux/termux-app#Important-Links" enorme >}}** dentro del mundo de Android y Linux. En la cual se puede encontrar muchísima información útil.

Con `Termux` se pueden hacer miles de cosas. 

<h1> Instalar Arch </h1>
{{< image src="termuxarch.jpg" >}}

<h1> Instalar herramientas de hacking ético </h1>
<p align="left">
<img width="40%" src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/toolx.png"/>
<img width="28.8%" src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/toolx_cat.png"/>
<img width="23.4%" src="https://raw.githubusercontent.com/rajkumardusad/Tool-X/master/core/Screenshot_2020-05-17-20-17-56.png"/>
</p>

<h1> y también customizarlo </h1>

{{< image src="https://raw.githubusercontent.com/xshin404/myTermux/main/assets/images/preview/nerdtree.png" >}}

---

# Instalando Termux

La aplicación de `Termux` la podemos encontrar facilmente en {{< link="https://f-droid.org/en/packages/com.termux/" "F-Droid" >}}. La versión de la <i>Play Store está obsoleta, y en Github, Termux recomiendo no instalar en lo absoluto la versión de allí.</i> Por lo tanto lo mejor es bajar el **APK** desde F-Droid.

Una vez instalada la aplicación, la abrimos y escribimos 
```bash
termux-setup-storage
```
Eso es para darle a `Termux` los permisos para acceder a nuestro Storage.

## Instalando los Dotfiles

Para dejar `Termux` bellisimo. Vamos a utilizar los **Dotfiles** de {{< link="https://github.com/xshin404/myTermux/" "xshin404" >}}


Así que vamos a ello. 
```bash
pkg update && pkg upgrade # Para actualizar termux y sus paquetes
```

```bash
pkg install ncurses-utils bc git
```

```bash
git clone https://github.com/xshin404/myTermux
```

```bash
cd myTermux
cp .xshin.var $HOME
chmod +x install.sh # le damos los permisos de ejecución
```

Para correr el script hay dos opciones **Full y Lightweight.** Para conocerlas basta con ejecutar `./install.sh help`
```bash
./install [options] # Hay dos opciones Full y Lightweight
```

Una vez hayamos instalado todo quedan los pasos finales:

```bash
cp -R .termux ~/ && termux-reload-settings # Para aplicar los ajustes
``` 

```bash
nvim

# Una vez dentro de neovim instalamos los plugins
:PackerInstall
```

## Comentarios finales

Eso es todo. Voy a dejar algunos comandos que son útiles y que disponemos ahora que ya hemos instalado los dotfiles

```bash
cava    # Visualizer
ncmpcpp # Reproductor de música local
nvim    # Editor de texto
chcolor # Para cambiar los colores
chfont  # Para cambias la fuente tipográfica
neo     # Neofetch fachero
ls      # En vez del natural ls, utilizamos 'exa'
```


# Espero que les haya gustado este post. Me ayudarían muchísimo comentando y compartiendo este post en donde sea: Grupos de Telegram, Redes Sociales, ustedes saben.-


<i> para poder ver algunos ajustes, como la batería, en neofetch vamos a necesitar Termux-Api (también lo encontramos en fdroid, y además de instalarlo como apk, debemos instalarlo con `pkg install termux-api`) </i>
