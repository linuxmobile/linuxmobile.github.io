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

## Uso

Para utilizar la herramienta no se necesita mucha inteligencia ni ser un completo experto en _seguridad informática_. Basta simplemente con ejecutar un par de comandos y saber que se está haciendo.

{% highlight bash %}  
`seeker -h`  
{% endhighlight %}

![](/uploads/seeker-h.png)

**Este comando arroja información de ayuda para saber como manejar** `seeker`

{% highlight bash %}  
`sudo seeker -t manual -s whatsapp`  
{% endhighlight %}

![](/uploads/seeker-template.png)

**En esta imagen podemos ver que el funcionamiento de** `seeker` **es muy básico, pero funciona perfectamente. Acá tenemos que elegir las opciones en mi caso utilicé la plantilla de Whatsapp**

![](/uploads/seeker-template2.png)

**Seleccionas un título para el grupo y luego una imagen de perfil. ¡Muy fácil!**

### Instalar y utilizar ngrok

En la última versión `Serveo` fue deshabilitado, así que debemos hacerlo de manera manual. Para esto utilizaremos `ngrok`

{% highlight bash %}  
`sudo pacman -S ngrok
# Arrancamos el servidor!
ngrok http 8080`  
{% endhighlight %}

**Una vez realizado esto y puesto en marcha el servidor, vamos a dirigirnos al link que nos genera** `ngrok`

![](/uploads/ngrok.png)

**En desktop vamos a obtener el mismo resultado que en el móvil, entras al link y como cualquier otro grupo de whatsapp. Se ve exactamente igual.**

![](/uploads/desktop.png)

Como verán `seeker` nos devuelve con muchísima exactitud la geolocalización de manera muy precisa.

![](/uploads/location.png)

## Errores

### Si pip3 no está instalado

{% highlight bash %}  
`sudo pacman -S python-pip`  
{% endhighlight %}

![](/uploads/pipnotinstalled.png)

### Si no tiene permisos para ejecutarse

{% highlight bash %}  
`# Solo para usuarios de ARCH
sudo chmod 777 /usr/share/seeker/arch_install.sh
sudo bash /user/share/seeker/arch_install.sh`  
{% endhighlight %}

# Obviamente, esta herramientas es únicamente con fines de aprendizaje y conocimiento.