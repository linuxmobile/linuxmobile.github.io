---
layout: post
featured: false
title: "¡Mis DOTFILES 2.0. Dejando DWM de manera impresionante!"
description: Termux, una de las mejores terminales para Android pero que luce un poco
  anticuada. Hoy te enseño como dejar Termux de la manera más linda posible!
date: 2022-01-30
image: https://i.imgur.com/rLKi68F.png
tags:
- Dotfiles
- Ricing
- Documentacion
- Linux

---
## Intro

*Ya hace un tiempo mostré mi Desktop en <strong>Archlinux</strong>. Estuve usando por un tiempo [Hypr](https://github.com/vaxerski/Hypr), y apesar de que es un WM increíble, siento que aún le falta un poco de trabajo. Así que tomé la decisión de pasarme a DWM, y la verdad que ha sido una de las mejores decisiones que he tomado en base a <strong>Arch</strong>. Así que lo que les traigo hoy es un breve "tutorial" para dejar Archlinux de la mejor manera posible.*

### Detalles

* **Window Manager** • [DWM ](https://github.com/siduck/chadwm)🎨 Tiles Everywhere!
* **Shell** • [Zsh ](https://www.zsh.org) 🐚 con [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) framework!
* **Terminal** • [ST ](https://github.com/siduck/st) 💻 Una terminal muy poderosa y con soporte a imagenes!
* **Panel** • [dwm-bar ](https://github.com/siduck/chadwm)🍧 Sencilla, sin lujos!
* **Compositor** • [Picom ](https://github.com/yshui/picom) 🍩 rounded corners y mucho BLUR!
* **Notify Daemon** • [Dunst ](https://github.com/dunst-project/dunst) 🍃 minimalista!
* **Launcher** • [Rofi ](https://github.com/davatorium/rofi) 🚀 Realmente rápido y customizable!
* **File Manager** • [Thunar](https://github.com/xfce-mirror/thunar) y [Ranger ](https://github.com/ranger/ranger)🔖 customizado!
* **GUI Basic-IDE** • [NVIM ](https://github.com/vlagh3/NvChad) 📝 Un IDE muy hermoso!

## Setup

### Dependencias y Paquetes

#### Paru como AUR HELPER 🆘:

Actualmente estoy utilizando [Paru](https://github.com/Morganamilo/paru), pero no tengo ninguna razón en específico. *Así que vamos a instalarlo*

{% highlight bash %}
# For Aur Helper install Paru
echo "### Installing paru as AUR Helper"
mkdir $HOME/Downloads/_cloned-repos
cd $HOME/Downloads/_cloned-repos
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si  
{% endhighlight %}

#### Dependencias 📦

{% highlight bash %}
echo "### Installing Required Packages"
paru -S python ffmpeg pipewire pipewire-alsa pipewire-pulse alsa-utils dunst       \
thunar thunar-archive-plugin thunar-volman ffmpegthumbnailer tumbler w3m neovim    \
viewnior mpv htop lxappearance picom-jonaburg-fix rofi rsync pavucontrol farge-git \
ranger python-pip noto-fonts-emoji noto-fonts-cjk xwallpaper scrot imlib2 fzf      \
exa bat file-roller gvfs gvfs-mtp htop imlib2 xclip ueberzug pacman-contrib cava   \
xorg-xsetroot simplescreenrecorder ytfzfim xdg-user-dirs catppuccin-gtk-theme      \
firefox noto-fonts libxft-bgra rofi-emoji xdotool xcolor
{% endhighlight %}

#### Oh-My-Zsh y Plugins 🐚

{% highlight bash %}
# First install Oh-My-Zsh 
echo "### Installing oh-my-zsh"  
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
echo "### Installing Oh-My-Zsh Plugins"
git clone --depth 1 https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone --depth 1 https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone --depth 1 https://github.com/zsh-users/zsh-completions.git ${ZSH_CUSTOM:~/.oh-my-zsh/custom}/plugins/zsh-completions  
{% endhighlight %}

#### Instalando las fuentes 🍉

{% highlight bash %}
echo -e "Descargando Nerdfonts..."
mkdir -p $HOME/Downloads/nerdfonts/
cd $HOME/Downloads/
wget https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/CascadiaCode.zip
wget https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/Iosevka.zip
wget https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/JetBrainsMono.zip
wget https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/Noto.zip
unzip '*.zip' -d $HOME/Downloads/nerdfonts/
rm -rf *.zip
{% endhighlight %}

{% highlight bash %} 
echo -e "Copiando las fonts a /usr/share/fonts/"
sudo cp -R $HOME/Downloads/nerdfonts/ /usr/share/fonts/
{% endhighlight %}

##### Clonamos y copiamos los DOTFILES 🌸

{% highlight bash %}
cd $HOME/Documents/
git clone --depth 1 https://github.com/linuxmobile/dwm-dots.git
rsync -avxHAXP --exclude '.git*' --exclude '*.md' dwm-dots/ ~/
{% endhighlight %}

{% highlight bash %}
### Contruimos dwm 
cd $HOME/lnxdwm/ && sudo make install 
### Contruimos ST (la terminal)
cd $HOME/st/ && sudo make install 
{% endhighlight %}



### Creditos

_A la hermosa comunidad de [r/unixporn](https://www.reddit.com/r/unixporn)._

**©** _A todos los artistas que crearon los iconos, ilustraciones, y wallpapers._

**©** _A cada uno que ha creado y mantiene los proyectos que he mencionado y utilizado anteriormente._

---

© [Owl4ce](https://github.com/owl4ce)
© [Ilham25](https://github.com/ilham25)
© [Siduck](https://github.com/siduck)
© [NvChad](https://github.com/NvChad)
