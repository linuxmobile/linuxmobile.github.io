---
layout: post
featured: true
title: Seeker. Una herramienta para obtener datos de GeoLocalización
description: Seeker, una herramienta para localizar con precisión cualquier móvil
  utilizando ingenería social.
date: 2020-08-21 03:00:00 +0000
image: "/images/posts/seeker.jpg"
tags:
- Documentacion
- Seguridad

---
## 1 Intro

El concepto detrás de `Seeker` es muy sencillo. Es una herramienta **muy facil de utilizar** que permite genera un sitio web falso alojado en Serveo, y que genera un enlace el cual al enviarlo a la _victima_ se le solicita **permisos de ubicación** y si el objetivo lo acepta ¡CHAZZZ!

Obtenemos:

* Longitud
* Latitud
* Presición
* Altitud
* Dirección
* Velocidad

Junto con estas opciones de `localización` obtenemos **Información sobre el dispositivo** \[Sin pedir permisos\]

* Sistema operativo
* Plataforma
* Número de núcleos
* Cantidad de ram aproximada
* Resolución de la pantalla
* Gpu
* Navegador
* Ip público

## 2 Es Diferente

Esta herramienta `seeker` es diferente a las convencionales herramientas conocidas como **Ip GeoLocation**, las cuales son herramientas que localizan la ubicación aproximada del ISP.

`Seeker` utiliza la API HTML para obtener la ubicación, y luego toma la latitud y longitud usando el GSP del dispositivo. Por lo cual `Seeker` funciona mucho mejor en móviles que en computadoras.

Generalmente si un usuario acepta la autorización de ubicación, la presición es de aproximadamente 30 metros.

## 3 Descarga

Existen varias formas de descargar esta herramienta. La más común es a través de `git`.

### Kali Linux / Ubuntu / Parrot OS

{% highlight bash %}
git clone https://github.com/thewhiteh4t/seeker.git cd seeker/ chmod 777 install.sh ./install.sh
{% endhighlight %}

### Termux

{% highlight bash %}
git clone https://github.com/thewhiteh4t/seeker.git cd seeker/ chmod 777 termux_install.sh ./termux_install.sh
{% endhighlight %}

### Instalación en Arch

Si eres un usuario de `Arch Linux` como yo, podemos agregar los repositorios de `Blackarch` _los cuales nos serviran en un futuro_.

**Primero que nada, debemos descargar un archivo desde la web oficial de** `BlackArch` [_https://blackarch.org/strap.sh_](https://blackarch.org/strap.sh "https://blackarch.org/strap.sh")

{% highlight bash %}
cd Downloads chmod 777 strap.sh sudo ./strap.sh sudo pacman -Syyu
{% endhighlight %}

Seguido, es tan simple de instalar haciendo:

{% highlight bash %}
sudo pacman -S seeker
{% endhighlight %}

![](/uploads/pacman-seeker.png)

**Por cierto, si les interesa saber que hay en el respositorio de** `BlackArch` **les dejo unos comandos que les serán muy útiles**

{% highlight bash %}  
`# Para ver todos los paquetes disponibles
sudo pacman -Sgg | grep blackarch | cut -d' ' -f2 | sort -u`  
{% endhighlight %}

{% highlight bash %}  
`# Para ver por categorías
sudo pacman -Sg | grep blackarch`  
{% endhighlight %}

![](/uploads/blackarch.png)

{% highlight bash %}  
  
{% endhighlight %}