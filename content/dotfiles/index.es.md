---
title: "DOTFILES"
date: 2021-01-31
draft: false

---

{{< admonition warning >}}
Éste artículo está bajo construcción. Pronto publicaré mi setup.
{{< /admonition >}}


<p align="center">
  <a name="top" href="#download">
     <img alt="linuxmobile/dotfiles" height="60%" width="100%" src="https://i.ibb.co/k4PbLjv/dotfiles.png"/>
  </a>
</p>

<p align="center">
  <a href="#setup">
    <img width="120px" style="padding: 0 10px;" src="https://i.ibb.co/b2VzWrg/setup.png"/>
  </a>
  <a href="#keybind">
    <img width="120px" style="padding: 0 10px;" src="https://i.ibb.co/Fgpgc2C/keybinds.png"/>
  </a>
  <a href="#gallery">
    <img width="120px" style="padding: 0 10px;" src="https://i.ibb.co/ZKTbkRy/gallery.png"/>
  </a>
  <a href="#users-configuration">
    <img width="120px" style="padding: 0 10px;" src="https://i.ibb.co/RznJp0s/user-conf.png"/>
  </a>
</p>

# Bienvenidos a todos, este es mi aporte con los dotfiles que utilizo día a día.

---

Esta es mi **configuración personal** basada en openbox. El dotfiles y el setup es 100% completo. Encontraran tanto mis aplicaciones favoritas como los ajustes necesarios para mi workflow. En mi caso utilizo `openbox` porque me ha resultado más cómodo a la hora de trabajar con múltiples ventanas y elementos. Anteriormente estaba utilizando BSPWM, pero decidí dejarlo de lado y enfocarme más en `openbox`. 

{{< admonition tip >}}
Pronto subiré un dotfiles/setup con la configuración para utilizar en `i3-gaps`
{{< /admonition >}}

---

Espero que puedan entender todo, y poder configurar sin problemas.

<a href="https://github.com/linuxmobile/dotfiles/">
  <img src="https://user-images.githubusercontent.com/53987136/110218451-6eba0b00-7eec-11eb-95bf-b9e3946fed9f.png" alt="minimal" align="right" width="400px"/>
</a>

Algunos detalles sobre el setup:
- **Window Manager**               • [Openbox](http://openbox.org/wiki/Main_Page) :art: Se pueden cambiar entre 4 modos!
- **Shell**                        • [Zsh](https://www.zsh.org/) :shell: con [oh my zsh](https://github.com/ohmyzsh/ohmyzsh) framework! <kbd>opcional pero recomendado</kbd>
- **Terminal**                     • [URxvt](http://software.schmorp.de/pkg/rxvt-unicode.html), [Termite](https://github.com/thestinger/termite) <kbd>disponible</kbd>
- **Openbox Menu**                 • [OBmenu-generator](https://github.com/trizen/obmenu-generator)
- **Panel**                        • [Tint2](https://gitlab.com/o9000/tint2) :shaved_ice: material icon font!
- **Compositor**                   • [Picom](https://github.com/yshui/picom) :doughnut: rounded corners!
- **Notify Daemon**                • [Dunst](https://github.com/dunst-project/dunst) :leaves: minimalismo!
- **Application Launcher**         • [Rofi](https://github.com/davatorium/rofi) :rocket: Un launcher super ligero y rápido!
- **File Manager**                 • [Thunar](https://github.com/xfce-mirror/thunar) :bookmark: customized sidebar & icon!
- **Music Player**                 • [Mpd](https://www.musicpd.org/) + [Ncmpcpp](https://github.com/ncmpcpp/ncmpcpp), [Spotify](https://www.spotify.com/us/download/linux/) :rice_scene: *riced!*
- **GUI & CLI IDE/Text Editor**    • [Geany](https://www.geany.org/), [Neovim](https://neovim.io/)

## Setup
Un paso a paso con la mejor manera de instalar este setup. Sigan los pasos al pie de la letra.

### Instalación (dependencias)

<a href="">
  <img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/072e191f-a0a5-4be2-bc7a-55eb140b254f/defdpeh-4b226af5-f035-4a5d-aedc-b9417b92563c.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvMDcyZTE5MWYtYTBhNS00YmUyLWJjN2EtNTVlYjE0MGIyNTRmXC9kZWZkcGVoLTRiMjI2YWY1LWYwMzUtNGE1ZC1hZWRjLWI5NDE3YjkyNTYzYy5wbmcifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.NHrNlWDMbuIVmHkpw4w6l0g7dMJGecLjxXsEPz1tHkI" alt="normal" align="right" width="400px"/>
</a>

{{< admonition tip >}}
No es necesario que instalen absolutamente todas las dependencias, pero en cuyo caso no lo hagan, les dará problemas para tener todo tal cual lo tengo instalado yo.
**Warning!** Esta configuración depende totalmente de `bash`, `sed`, `awk`, y `coreutils`.  
Doy por sentado que estamos usando [`sudo`](https://www.sudo.ws/) o [`doas`](https://github.com/Duncaen/OpenDoas).
{{< /admonition >}}

<details open>
<summary><strong>Debian & Ubuntu (and all based distributions)</strong></summary>
  
```sh
sudo apt install rsync python psmisc x11-utils imagemagick ffmpeg wireless-tools openbox pulseaudio \
alsa-utils brightnessctl nitrogen dunst tint2 gsimplecal rofi qt5-style-plugins lxpolkit xautolock rxvt-unicode \
xclip scrot thunar thunar-archive-plugin thunar-media-tags-plugin thunar-volman ffmpegthumbnailer tumbler \
viewnior mpv mpd mpc ncmpcpp pavucontrol parcellite neofetch w3m w3m-img htop playerctl xsettingsd
```
</details>

<details>
  <summary>oh-my-zsh & plugins <kbd>optional</kbd></summary>
  
```sh
sudo apt install zsh &&
chsh -s $(command -v zsh) &&
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" &&
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting &&
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions &&
git clone https://github.com/zsh-users/zsh-completions.git ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
```
</details>
  
<details>
<summary>picom</summary>
    
```sh
sudo apt install meson libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev \
libxcb-render-util0-dev libxcb-render0-dev libxcb-randr0-dev libxcb-composite0-dev libxcb-image0-dev \
libxcb-present-dev libxcb-xinerama0-dev libxcb-glx0-dev libpixman-1-dev libdbus-1-dev libconfig-dev \
libgl1-mesa-dev libpcre2-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev
```
```sh
git clone https://github.com/yshui/picom.git &&
cd picom/ && git submodule update --init --recursive &&
   meson --buildtype=release . build &&
ninja -C build &&
   ninja -C build install
```
</details>

<details>
<summary>obmenu-generator</summary>
  
> I haven't tested it yet.
  
```sh
sudo su
```
```sh
echo 'deb http://download.opensuse.org/repositories/home:/Head_on_a_Stick:/obmenu-generator/Debian_10/ /' > /etc/apt/sources.list.d/home:Head_on_a_Stick:obmenu-generator.list &&
wget -nv https://download.opensuse.org/repositories/home:Head_on_a_Stick:obmenu-generator/Debian_10/Release.key -O Release.key &&
apt-key add - < Release.key &&
apt update &&
apt install obmenu-generator libgtk2-perl
```
    
[See Installation from Git](https://github.com/trizen/obmenu-generator/blob/master/INSTALL.md)
  
</details>


<details open>
  <summary><strong>Arch Linux (y basadas en)</strong></summary>

{{< admonition tip >}}
Asegurate que tu **AUR Helper** es [`yay`](https://github.com/Jguer/yay) or [`paru`](https://github.com/Morganamilo/paru).
{{< /admonition >}}

```sh
yay -S rsync python psmisc xorg-xprop xorg-xwininfo imagemagick ffmpeg wireless_tools openbox \
pulseaudio pulseaudio-alsa alsa-utils brightnessctl nitrogen dunst tint2 gsimplecal rofi qt5-styleplugins \
lxsession xautolock rxvt-unicode-patched xclip scrot thunar thunar-archive-plugin thunar-volman \
thunar-media-tags-plugin ffmpegthumbnailer tumbler viewnior mpv mpd mpc ncmpcpp pavucontrol \
parcellite neofetch w3m htop picom-git obmenu-generator gtk2-perl playerctl xsettingsd
```

</details>
  
<details>
<summary>oh-my-zsh & plugins <kbd>opcional</kbd></summary>
  
```sh
sudo pacman -S zsh &&
chsh -s $(command -v zsh) &&
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" &&
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting &&
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions &&
git clone https://github.com/zsh-users/zsh-completions.git ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
```
</details>

<br>

<details>
  <summary><strong>Otras distribuciones de Linux</strong></summary>
  
   Customiza y cambia las dependencia dependiendo de tu SO!  
   
**Por ejemplo**  
- [Gentoo/Linux](https://packages.gentoo.org/)  
- [Void (Linux)](https://voidlinux.org/packages/)
</details>
  
  <br>

**Opcional**: [betterdiscord](https://betterdiscord.net/), [file-roller](https://wiki.gnome.org/Apps/FileRoller), [geany](https://geany.org/) + [geany plugins](https://plugins.geany.org/), [gimp](https://www.gimp.org/), [lxappearance](https://wiki.lxde.org/en/LXAppearance), [nano](https://www.nano-editor.org/) + [nano syntax highlighting](https://github.com/scopatz/nanorc), [neovim](https://neovim.io/), [obconf](http://openbox.org/wiki/ObConf:About), [slim](https://wiki.archlinux.org/index.php/SLiM), [spotify](https://www.spotify.com/us/download/linux/), [termite](https://www.compuphase.com/software_termite.htm), [xfce4-power-manager](https://docs.xfce.org/xfce/xfce4-power-manager/getting-started).


## Instalación (dotfiles) 
  
<details open>
Puedes clonar o descargar como un .Zip. Luego de esto copia todos los archivos de la carpeta **dotfiles** al directorio $HOME de tu usuario.
> Asumiendo que estás clonando el repositorio en `~/Documents` 

```sh
git clone https://github.com/linuxmobile/dotfiles.git && cd dotfiles/
```
   
Recomiendo utilizar rsync.
```sh
rsync -avxHAXP --exclude '.git*' .* ~/
```
**Explicación breve**
| Opción    | Función                                             |
|:---------:|-----------------------------------------------------|
| -a        | todos los archivos, con permisos, etc.              |
| -v        | verbose, mencionar los archivos                     |
| -x        | mismo sistema de archivos                           |
| -H        | preserve hard links (no incluído con  -a)           |
| -A        | preserve ACLs/permissions (no incluído en -a)       |
| -X        | preserve extended attributes (no incluído en -a)    |
| -P        | mostrar progreso                                    |
| --exclude | excluir archivos                                    |

**Diferencias**  
- `cp` es para duplicar cosas y, de forma predeterminada, solo garantiza que los archivos tengan nombres de ruta completos únicos.
- `rsync` es para sincronizar cosas y usa el tamaño y la marca de tiempo de los archivos para decidir si deben reemplazarse. Tiene muchas más opciones y capacidades que `cp`.

</details>

<details open>
  <summary><strong>Icons</strong></summary>
  
```sh
cd ~/.icons && tar -Jxvf Papirus-Custom.tar.xz && tar -Jxvf Papirus-Dark-Custom.tar.xz &&
sudo ln -s ~/.icons/Papirus-Custom /usr/share/icons/Papirus-Custom &&
sudo ln -s ~/.icons/Papirus-Dark-Custom /usr/share/icons/Papirus-Dark-Custom
```

**¿Por qué necesito vincular los iconos a los recursos del sistema del usuario?** :thinking:  
Dunst lo necesita para mostrar la mayor parte del icono de la notificación generada por la aplicación.
  </details>
  
<details open>
  <summary><strong>Referescar el Cache de las Fuentes</strong></summary>
  
```sh
fc-cache -rv
```
    
</details>

<details open>
<summary><strong>Privilegios Root con <a href="https://en.wikipedia.org/wiki/Setuid#SUID">SUID</a></strong></summary>
   
- `brightnessctl`
- *otros también son necesarios*
   
Para `brightnessctl`, yo recomiendo [agregar los usuarios a grupo de videos](https://wiki.archlinux.org/index.php/Users_and_groups#Group_management).
   
```sh
sudo chmod u+s $(command -v brightnessctl)
```

</details>

### El paso que estas esperando
El último paso es iniciar sesión en openbox-session, básicamente iniciar sesión desde el administrador de pantalla que usa, como lightdm, gdm, etc.
Si estás usando `~/.xinitrc` sin display manager, solamente añade

**Systemd Linux Distribution**  
```sh
exec openbox-session
```

**Init-Freedom Linux Distribution**  
```sh
exec dbus-launch --exit-with-session openbox-session
```

## Adicionales

**Te recomiendo habilitar este comando**
- `ls` ➜ [`exa`](https://github.com/ogham/exa)  

[`~/.zshrc`](./.zshrc)  
```zsh
...
131 alias ls="exa -lgh --icons --group-directories-first"
132 alias la="exa -lgha --icons --group-directories-first"
...
```

- `cat` ➜ [`bat`](https://github.com/sharkdp/bat)

 
- **Las preferencias de usuario <kbd>requeridas</kbd>**  
  [`~/.linuxmobile_var`](./.linuxmobile_var)  
  En este lugar se manejan casi todas las configuración de usuario. Están comentadas, y espero que sean fácil de entender. ^^
  
- **User's Tray Icons**  
  [`~/.config/openbox/tray`](./.config/openbox/tray)  
  Un ejemplo es habilitar `nm-applet`, ya que yo utilizo [networkmanager_dmenu](./.local/bin/networkmanager_dmenu)

Quita los hashtags de todo lo que necesitas, y luego reinicia la sesion en openbox

- **Aplicaciones por default disponibles**  
  [` ~/.scripts/default-apps/list`](./.scripts/default-apps/list)
  - **Terminal**: `urxvt` `termite`
  - **Lockscreen**: *cualquiera*
  - **Music Player**: `mpd` `spotify`
  - **File Manager**: *cualquiera*
  
```cfg
1 terminal="urxvt"
2 lockscreen="slimlock"
3 musicpl="mpd"
4 filemanager="thunar"
```

- **Neovim**  
[`~/.config/nvim/`](./.config/nvim/)  
Supongo que ya sabes que hacer con [Vim-plug](https://github.com/junegunn/vim-plug).
  
- **MPD Music Directory**  
  [`~/.mpd/mpd.conf`](./.mpd/mpd.conf)
```cfg
...
6 music_directory     "~/Music"
...
```
  
- **Ncmpcpp Music Directory**  
Auto connect with MPD.
  
**Cómo usar ncmpcpp albumart?** (URxvt)  
Es fácil pon tu `album|cover|folder|artwork|front.jp?g|png|gif|bmp` en la carpeta con las canciones del album. La imágen recomendada es de  *500px* ( **1:1** ) o más. [See keybinds](https://github.com/owl4ce/dotfiles/wiki/Keybinds#ncmpcpp)


- **Neofetch Image**  
[`~/.config/neofetch/config.conf`](./.config/neofetch/config.conf`)
```cfg
...
641 # Image Source
642 #
643 # Which image or ascii file to display.
644 #
645 # Default:  'auto'
646 # Values:   'auto', 'ascii', 'wallpaper', '/path/to/img', '/path/to/ascii', '/path/to/dir/'
647 #           'command output (neofetch --ascii "$(fortune | cowsay -W 30)")'
648 # Flag:     --source
649 #
650 # NOTE: 'auto' will pick the best image source for whatever image backend is used.
651 #       In ascii mode, distro ascii art will be used and in an image mode, your
652 #       wallpaper will be used.
653 #image_source="auto"
654 #image_source="${HOME}/.config/neofetch/images/arch.png"
655 #image_source="${HOME}/.config/neofetch/images/arch_dark.png"
656 #image_source="${HOME}/.config/neofetch/images/artix.png"
657 #image_source="${HOME}/.config/neofetch/images/bedrock.png"
658 #image_source="${HOME}/.config/neofetch/images/gentoo.png"
659 #image_source="${HOME}/.config/neofetch/images/gentoo_dark.png"
660 #image_source="${HOME}/.config/neofetch/images/lofi.png"
661 image_source="${HOME}/.config/neofetch/images/sakura.png"
662 #image_source="${HOME}/.config/neofetch/images/ubuntu.png"
663 #image_source="${HOME}/.config/neofetch/images/ubuntu_dark.png"
664 #image_source="${HOME}/.config/neofetch/images/void.png"
665 #image_source="${HOME}/.config/neofetch/images/void_dark.png"
...
```

## :confetti_ball:  Creditos / Gracias
- **Inspiration and resources**
  - [OWL4CE](https://github.com/owl4ce)
  - [Elena](https://github.com/elenapan)
  - [Adhi Pambudi](https://github.com/addy-dclxvi)
  - [Fikri Omar](https://github.com/fikriomar16)
  - [Nanda Oktavera](https://github.com/okitavera)
  - [Rizqi Nur Assyaufi](https://github.com/bandithijo)
  - [Muktazam Hasbi Ashidiqi](https://github.com/reorr)
  - [Galih Wisnuaji](https://github.com/nekonako)
  - [owl4ce](https://github.com/owl4ce)
  - [Ghani Rafif](https://github.com/ekickx)
  - [Aditya Shakya](https://github.com/adi1090x)
  - ?

- **Knowledge and other resources**
  - [Digital Synopsis](https://digitalsynopsis.com/)
  - [Wiki @ Openbox](http://openbox.org/wiki/Help:Themes)
  - [Pango Markup @ Gnome](https://developer.gnome.org/pango/stable/pango-Markup.html)
  - [Custom Environment @ ArchWiki](https://wiki.archlinux.org/index.php/desktop_environment#Custom_environments)
  - [Pure Bash Bible](https://github.com/dylanaraps/pure-bash-bible)
  - [Stark's Color Scripts](https://github.com/stark/Color-Scripts)
  - [Notify Send (bash)](https://github.com/vlevit/notify-send.sh)
  - [NetworkManager Dmenu](https://github.com/firecat53/networkmanager-dmenu)
  - [URxvt Manual](https://linux.die.net/man/1/urxvt)
  - [URxvt Resize Font](https://github.com/simmel/urxvt-resize-font)
  - [URxvt Tabbed Extended](https://github.com/mina86/urxvt-tabbedex)
  - [Showing Album Cover in Ncmpcpp](https://marcocheung.wordpress.com/2015/08/09/showing-album-cover-in-ncmpcpp/)
  - [Complete List of GitHub Markdown Emoji Markup](https://gist.github.com/rxaviers/7360908)
  - Many GNU/Linux and Unix forums.
    
- **Softwares**
  - [Geany - The Flyweight IDE](https://www.geany.org/)
  - [GIMP - GNU Image Manipulation Program](https://www.gimp.org/)
  - [Gpick - Advanced Color Picker](http://www.gpick.org/)
  - [Themix - GUI Theme Designer](https://github.com/themix-project/oomox)
  - Tint2conf, etc.

- **© All artist who make icons, illustrations, and wallpapers.**
  
  The original source that I found:
  - [Gladient Icons](https://play.google.com/store/apps/details?id=com.maxghani.gladient)
  - [桜](https://www.pixiv.net/en/artworks/80518034)
  - [桜セイバー沖田総司](https://www.pixiv.net/en/artworks/59740059)
  - [沖田総司](https://www.pixiv.net/en/artworks/62996457)
  - [owl4ce](https://github.com/owl4ce)

