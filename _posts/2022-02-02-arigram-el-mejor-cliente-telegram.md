---
layout: post
featured: false
title: "Arigram. El mejor cliente para Telegram"
description: Hoy les traigo Arigram, el mejor cliente de Telegram que he probado en años. 
date: 2022-02-02
image: https://i.imgur.com/Ca7ppiz.png
tags:
- Documentacion
- Telegram
---

### Intro 

Hoy quiero enseñarles como instalar [Arigram](https://github.com/TruncatedDinosour/arigram), un cliente de Telegram por Terminal. 

![](https://i.imgur.com/Ca7ppiz.png)

### Instalación

*Para instalar solo vamos a precisar de pocos paquetes. Python, pip, poetry.*

{% highlight bash %}
sudo pacman -S python
python -m pip install --upgrade pip
pip install poetry
{% endhighlight %}

#### Clonamos el repositorio

{% highlight bash %}
mkdir -p ~/.local/src
cd ~/.local/src
git clone https://github.com/TruncatedDinosour/arigram.git
cd arigram
./do local
{% endhighlight %}

##### Fix "traceback... error"

*Si les sale un error que comienza con traceback...*

{% highlight bash %}
python -m ensurepip --upgrade 
python3 -m pip install --upgrade pip
{% endhighlight %}

**Y continuamos con `./do local`**

#### Agregamos .local/bin al path

*Si no estás utilizando zsh, solo cambia el .zshrc por tu shell...*

{% highlight bash %}
echo -n 'export PATH="${PATH}:${HOME}/.local/bin"' >> ~/.zshrc
{% endhighlight %}

---

Eso es, practicamente, todo. Ya puedes iniciar telegram con el comando `arigram`. 
Pero, para poder configurar un poco más y entender mejor como funciona este cliente. Les dejo algunos ajustes, y el **keybind**.

## Keybind

#### Chat

- `j,k`: Moverse para arriba/abajo 
- `J,K`: Mueven 10 chats para arriba/abajo
- `g`: Ir al top (chat)
- `l`: Abrir mensaje del chat
- `m`: Mutear y desmutear el chat
- `p`: Anclar/desanclar chat
- `u`: Marcar como leído/no leído
- `r`: Leer el chat actual
- `c`: Mostrar la lista de contactos
- `dd`: Borrar chat, o historial de conversación
- `ng`: Crear un nuevo grupo
- `ns`: Crear un chat secreto
- `/`: Buscar en los chats
- `?`: Mostrar la ayuda

#### Mensajes

- `j,k`: Mover arriba/abajo 
- `J,K`: Mover 10 mensajes arriba/abajo
- `G`: Mover al mensaje más reciente
- `D`: Descargar archivo
- `l`: Si es un video, imagen o documento, entonces abrir en la siguiente app (configurada en el mailcap) por ejemplo:

{% highlight ini %}
# Images
image/png; viewnior "%s"
audio/*; mpv "%s"
{% endhighlight %}


- `e`: Editar el mensaje 
- `<space>`: select msg and jump one msg down (use for deletion or forwarding)
- `<ctrl+space>`: same as space but jumps one msg up
- `y`: yank (copy) selected msgs with <space> to internal buffer (for forwarding) and copy current msg text or path to file to clipboard
- `p`: forward (paste) yanked (copied) msgs to current chat
- `dd`: delete msg for everybody (multiple messages will be deleted if selected)
- `i or a`: insert mode, para escribir un nuevo mensaje
- `I or A`: Abrir en vim para enviar un mensaje más largo
- `v`: Grabar y enviar un audio
- `r,R`: Responder mensaje
- `sv`: Enviar videos
- `sa`: Enviar audios
- `sp`: Enviar imagenes
- `sd`: Enviar documentos
- `o`: Abrir la URL del mensaje seleccionado (if multiple urls, `urlview` will be opened)
- `]`: Chat siguiente
- `[`: Chat previo
- `u`: Mostrar la info del usuario (username, bio, phone, etc.)
- `c`: Mostrar la info del chat (e.g. secret chat encryption key, chat id, state, etc.)
- `?`: Mostrar ayuda
- `!`: open msg with custom cmd

### mailcap

* El mailcap, es un archivo de configuración. Sencillo. Donde seleccionaremos que apps queremos que se usen. Algo así como el "abrir con:".*

![mailcap file](https://i.imgur.com/MXgMcUS.png)

{% highlight ini %}
# media
video/*; mpv "%s"
audio/ogg; mpv --speed=1.33 "%s"
audio/mpeg; mpv --no-video "%s"
image/*; viewnior "%s"

# text
text/html; w3m "%s"
text/html; open -a firefox "%s"
text/plain; less "%s"

# fallback to vim
text/*; nvim "%s"
{% endhighlight %}
* Así está configurado mi mailcap*

### El archivo de configuración 

*[Arigram](https://github.com/TruncatedDinosour/arigram) Es bastante configurable Por lo tanto, dentro de la carpeta `$HOME/.config/arigram/` podemos ver el archivo config.py. Ahí vamos a configurar algunas cosas.*

![Arigram Config](https://i.imgur.com/RfdjF2S.png)

#### Algunas configuraciones importantes

{% highlight python %}
MAILCAP_FILE: "~/.mailcap"
{% endhighlight %}

{% highlight python %}
MAX_DOWNLOAD_SIZE: str = "10MB"
{% endhighlight %}

{% highlight python %}
CHAT_FLAGS = {
    "online": "●",
    "pinned": "📍",
    "muted": "🔇",
    # chat is marked as unread
    "unread": "U",
    # last msg haven't been seen by recipient
    "unseen": "✓",
    "secret": "🔒",
    "seen": "✅",  # leave empty if you don't want to see it
}
MSG_FLAGS = {
    "selected": "*",
    "forwarded": "F",
    "new": "N",
    "unseen": "U",
    "edited": "E",
    "pending": "...",
    "failed": "💩",
    "seen": "✅",  # leave empty if you don't want to see it
}
{% endhighlight %}

---

**Por cierto, si querés encontrar mis ajustes. Los tengo todos alojados en [Github](https://github.com/linuxmobile/dwm-dots). (Incluyendo, este config.py)**


#### Un breve cierre.

Bueno, esto ha sido todo por hoy. La verdad que llevaba mucho tiempo utilizando [Telegram-Desktop](https://github.com/telegramdesktop/tdesktop), la versión que ya todos conocemos. Pero con el fin de minimizar, un poco, la contaminación visual y las distracciones decidí pasarme a una versión TUI. *Esta versión de Arigram, aún le faltan algunas características* pero es un excelente cliente. Consume muy pocos recursos. Es liviano. El lenguaje es sencillo. Tiene muchísimo potencial. *Cabe destacar que está basado en el trabajo de [paul-nameless](https://github.com/paul-nameless/tg).* Así que, te agradecería si pudieras compartir este post. Y que dejes algún comentario!

**©** *[TruncatedDinosour](https://github.com/TruncatedDinosour/arigram)*

