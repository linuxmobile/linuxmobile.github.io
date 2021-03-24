---
weight: 1
title: "Seeker. Una herramienta para obtener datos de GeoLocalización"
date: 2020-08-21
lastmod: 2020-08-21
draft: false
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "Seeker, una herramienta para localizar con precisión cualquier móvil utilizando ingenería social."
resources:
- name: "featured-image"
  src: "seeker.jpg"

tags: ["seguridad", "herramienta"]
categories: ["seguridad", "documentation"]

lightgallery: true

toc:
  auto: false
---

Seeker, una herramienta para localizar con precisión cualquier móvil utilizando ingenería social.

<!--more-->


## 1 Intro {#intro}


El concepto detrás de `Seeker` es muy sencillo. Es una herramienta **muy facil de utilizar** que permite genera un sitio web falso alojado en Serveo, y que genera un enlace el cual al enviarlo a la *victima* se le solicita **permisos de ubicación** y si el objetivo lo acepta ¡CHAZZZ!

Obtenemos:

* Longitud
* Latitud
* Presición
* Altitud
* Dirección
* Velocidad

Junto con estas opciones de `localización` obtenemos **Información sobre el dispositivo** [Sin pedir permisos]

* Sistema operativo
* Plataforma
* Número de núcleos
* Cantidad de ram aproximada
* Resolución de la pantalla
* Gpu
* Navegador
* Ip público



## 2 Es Diferente {#novedades}

Esta herramienta `seeker` es diferente a las convencionales herramientas conocidas como **Ip GeoLocation**, las cuales son herramientas que localizan la ubicación aproximada del ISP.

`Seeker` utiliza la API HTML para obtener la ubicación, y luego toma la latitud y longitud usando el GSP del dispositivo. Por lo cual `Seeker` funciona mucho mejor en móviles que en computadoras.

Generalmente si un usuario acepta la autorización de ubicación, la presición es de aproximadamente 30 metros. 

## 3 Descarga {#descarga}

Existen varias formas de descargar esta herramienta. La más común es a través de `git`.

### Kali Linux / Ubuntu / Parrot OS

```zsh
git clone https://github.com/thewhiteh4t/seeker.git
cd seeker/
chmod 777 install.sh
./install.sh
```

### Termux

```Sheel
git clone https://github.com/thewhiteh4t/seeker.git
cd seeker/
chmod 777 termux_install.sh
./termux_install.sh
```

### Instalación en Arch

Si eres un usuario de `Arch Linux` como yo, podemos agregar los repositorios de `Blackarch` *los cuales nos serviran en un futuro*.

**Primero que nada, debemos descargar un archivo desde la web oficial de** `BlackArch` *https://blackarch.org/strap.sh*

```zsh
cd Downloads
chmod 777 strap.sh
sudo ./strap.sh
sudo pacman -Syyu
```
Seguido, es tan simple de instalar haciendo:

```zsh
sudo pacman -S seeker
```
{{< image src="pacman-seeker.png" >}}

**Por cierto, si les interesa saber que hay en el respositorio de** `BlackArch` **les dejo unos comandos que les serán muy útiles**


```zsh
# Para ver todos los paquetes disponibles
sudo pacman -Sgg | grep blackarch | cut -d' ' -f2 | sort -u
```
```zsh
# Para ver por categorías
sudo pacman -Sg | grep blackarch
```
{{< image src="blackarch.png" >}}

## Uso {#uso}

Para utilizar la herramienta no se necesita mucha inteligencia ni ser un completo experto en *seguridad informática*. Basta simplemente con ejecutar un par de comandos y saber que se está haciendo.

```zsh
seeker -h
```
{{< image src="seeker-h.png" >}}

**Este comando arroja información de ayuda para saber como manejar** `seeker`


```zsh
sudo seeker -t manual -s whatsapp
```
{{< image src="seeker-template.png" >}}

**En esta imagen podemos ver que el funcionamiento de** `seeker` **es muy básico, pero funciona perfectamente. Acá tenemos que elegir las opciones en mi caso utilicé la plantilla de Whatsapp**

{{< image src="seeker-template2.png" >}}
**Seleccionas un título para el grupo y luego una imagen de perfil. ¡Muy fácil!**

### Instalar y utilizar ngrok

En la última versión `Serveo` fue deshabilitado, así que debemos hacerlo de manera manual. Para esto utilizaremos `ngrok`

```zsh
sudo pacman -S ngrok
# Arrancamos el servidor!
ngrok http 8080
```
**Una vez realizado esto y puesto en marcha el servidor, vamos a dirigirnos al link que nos genera** `ngrok`
{{< image src="ngrok.png" >}}


**En desktop vamos a obtener el mismo resultado que en el móvil, entras al link y como cualquier otro grupo de whatsapp. Se ve exactamente igual.**
{{< image src="desktop.png" >}}

**En ambos dispositivos, te pide permisos de ubicación y una vez que lo aceptas el resultado es increíblemente exacto!**
{{< image src="mobile2.png" >}}


Como verán `seeker` nos devuelve con muchísima exactitud la geolocalización de manera muy precisa.

{{< image src="location.png" >}}

{{< image src="maps.png" >}}

---

## Errores {#errores}

### Si pip3 no está instalado
{{< image src="pipnotinstalled.png" >}}
```zsh
sudo pacman -S python-pip
```

### Si no tiene permisos para ejecutarse

```zsh
# Solo para usuarios de ARCH
sudo chmod 777 /usr/share/seeker/arch_install.sh
sudo bash /user/share/seeker/arch_install.sh
```


# Obviamente, esta herramientas es únicamente con fines de aprendizaje y conocimiento.
