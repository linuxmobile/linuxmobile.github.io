---
weight: 1
title: "KTweak un nuevo mod para tu kernel"
date: 2020-08-22T14:50:00
lastmod: 2020-08-22
draft: draft
author: "Braian A. Diez"
authorLink: "https://linuxmobile.github.io"
description: "KTweak es un mod para optimizar el rendimiento de tu kernel en Android."
resources:
- name: "featured-image"
  src: "kernel.jpg"

tags: ["kernel", "android"]
categories: ["android", "documentation"]

lightgallery: true

toc:
  auto: false
---

KTweak es un mod para optimizar el rendimiento de tu kernel en Android.


<!--more-->


El desarrollador (muy reconocido en `XDA`)  {{< link "https://github.com/tytydraco" tytydraco >}} ha creado un **módulo de magisk**  llamado `KTweak` el cual sirve como modificador universal del kernel.

En comparación con otros "optimizadores" `KTweak` está basado en ajustes reales y con evidencia para optimizar verdaderamente el kernel del dispositivo. 

`KTweak` compara algunos ejemplos cómo:
* `LSpeed` utiliza al menos 4000 líneas de código, lo cuál es demasiado e innecesario.
* `NFS Injector` está compilado con binarios y utiliza código cerrado. 
* `LKT` Configura variables del **build.prop** sin que sea necesario y que probablemente no existen.
* `MAGNETAR` utiliza binarios compilados que se instalan dentro de /system/etc. 

`KTweak`  se diferencia por:
* Tener alrededor de 200 líneas de código.
* Ser OpenSource.
* Estar respaldado por lógica y evidencia real.
* Ser diseñado por un **desarrollador de kernel experimentado**.
* No ser intrusivo con el sistema.


**En el repositorio de {{< link "https://github.com/Magisk-Modules-Alt-Repo/ktweak" Magisk >}} se explica extensivamente y de manera muy detallada todo lo que el kernel hace. A diferencia de otros "optimizadores" puedo decir que es muy concisa la información y correcta.**

Pueden descargarlo de manera muy sencilla desde el link de `{{< link "https://github.com/Magisk-Modules-Alt-Repo/ktweak" Magisk >}}`

{{< image src="magisk.png" >}}


