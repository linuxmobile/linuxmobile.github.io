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

### Configurando...

A este punto, ya tenemos instalado todo lo necesario para que **vscode** funcione.
Vamos a proceder abriendo **vscode**.

![Welcome Page en vscode](https://i.imgur.com/YoJIMbk.png)

#### Extensiones (mis recomendaciones)

**Para pegar el código es suficiente con hacer `Ctrl+P` y luego pegar el código.**

[AutoCloseTag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)

![](https://github.com/formulahendry/vscode-auto-close-tag/raw/HEAD/images/usage.gif)

{% highlight shell %}
ext install formulahendry.auto-close-tag
{% endhighlight %}

[ColorHighlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)

![](https://i.imgur.com/Xtl6NQ4.png)

{% highlight shell %}
ext install naumovs.color-highlight
{% endhighlight %}

[ErrorLens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)

![](https://raw.githubusercontent.com/usernamehw/vscode-error-lens/master/img/demo.png)

{% highlight shell %}
ext install usernamehw.errorlens
{% endhighlight %}

[EsLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

{% highlight shell %}
ext install dbaeumer.vscode-eslint
{% endhighlight %}

[GitCommitPlugin](https://marketplace.visualstudio.com/items?itemName=redjue.git-commit-plugin)

![](https://github.com/RedJue/git-commit-plugin/raw/HEAD/assets/open.gif)

{% highlight shell %}
ext install redjue.git-commit-plugin
{% endhighlight %}

[GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

![](https://raw.githubusercontent.com/eamodio/vscode-gitlens/main/images/docs/revision-navigation.gif)

{% highlight shell %}
ext install eamodio.gitlens
{% endhighlight %}

[PathIntellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

![](https://i.giphy.com/iaHeUiDeTUZuo.gif)

{% highlight shell %}
ext install christian-kohler.path-intellisense
{% endhighlight %}

[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

![](https://i.imgur.com/WB7tnvT.png)

{% highlight shell %}
ext install esbenp.prettier-vscode
{% endhighlight %}

#### Temas e Iconos (opcional)

[Catppuccin](https://marketplace.visualstudio.com/items?itemName=Catppuccin.catppuccin-vsc)

![](https://raw.githubusercontent.com/catppuccin/vscode/main/assets/ss.png)

{% highlight shell %}
ext install Catppuccin.catppuccin-vsc
{% endhighlight %}

[Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

![](https://i.imgur.com/spgqrNt.png)

{% highlight shell %}
ext install PKief.material-icon-theme
{% endhighlight %}

[Material Product Icons](https://marketplace.visualstudio.com/items?itemName=PKief.material-product-icons)

![](https://raw.githubusercontent.com/PKief/vscode-material-product-icons/main/images/preview-explorer.png)

{% highlight shell %}
ext install PKief.material-product-icons
{% endhighlight %}

#### Configurando vscode .json

![](https://i.imgur.com/T7D02kQ.png)
**Para abrir los ajustes es suficiente con hacer `Ctrl+Shift+P` y escribir `settings`.**

![](https://i.imgur.com/ifo1JiX.png)

{% highlight json %}
{
    "editor.inlineSuggest.enabled": true,
    "workbench.startupEditor": "newUntitledFile",
    "workbench.colorTheme": "Catppuccin",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.productIconTheme": "material-product-icons",
    "files.autoSave": "afterDelay",
    "editor.fontligatures": true,
    "editor.fontFamily": "'CaskaydiaCove NF', 'Cascadia Code PL', 'Cascadia Code', Consolas, 'Courier New', monospace",
    "editor.codeLensFontFamily": "'CaskaydiaCove NF', Consolas, 'Courier New', monospace",
    "editor.guides.bracketPairs": true,
    "editor.renderIndentGuides": true,
    "editor.bracketPairsColorization.enabled": true,
    "telemetry.telemetryLevel": "off",
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "explorer.confirmDelete": false,
    "git.autofetch": true,
    "editor.cursorBlinking": "expand",
    "git.enableSmartCommit": true,
    "git.confirmSync": false,
}
{% endhighlight %}

## Y por último...

Bueno, sinceramente eso ha sido todo por hoy. Tengo preparado un post para publicar en esta semana.
Y es acerca de **Github Copilot**. Pero hablaremos de eso más adelante. Espero que les haya servido
de ayuda este post. Y bueno, ¡espero sus comentarios!
