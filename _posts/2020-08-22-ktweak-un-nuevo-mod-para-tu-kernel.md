---
layout: post
title: KTweak un nuevo mod para tu kernel
description: KTweak es un mod para optimizar el rendimiento de tu kernel en Android.
date: 2020-08-22T03:00:00.000+00:00
image: https://images.unsplash.com/photo-1607252650355-f7fd0460ccdb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80
tags:
- Documentacion
- Android

---
El desarrollador (muy reconocido en `XDA`) [tytydraco](https://github.com/tytydraco) ha creado un **módulo de magisk** llamado `KTweak` el cual sirve como modificador universal del kernel.

En comparación con otros “optimizadores” `KTweak` está basado en ajustes reales y con evidencia para optimizar verdaderamente el kernel del dispositivo.

`KTweak` compara algunos ejemplos cómo:

* `LSpeed` utiliza al menos 4000 líneas de código, lo cuál es demasiado e innecesario.
* `NFS Injector` está compilado con binarios y utiliza código cerrado.
* `LKT` Configura variables del **build.prop** sin que sea necesario y que probablemente no existen.
* `MAGNETAR` utiliza binarios compilados que se instalan dentro de /system/etc.

`KTweak` se diferencia por:

* Tener alrededor de 200 líneas de código.
* Ser OpenSource.
* Estar respaldado por lógica y evidencia real.
* Ser diseñado por un **desarrollador de kernel experimentado**.
* No ser intrusivo con el sistema.

**En el repositorio de** [**Magisk**](https://github.com/Magisk-Modules-Alt-Repo/ktweak) **se explica extensivamente y de manera muy detallada todo lo que el kernel hace. A diferencia de otros “optimizadores” puedo decir que es muy concisa la información y correcta.**

Pueden descargarlo de manera muy sencilla desde el link de [`Magisk`](https://github.com/Magisk-Modules-Alt-Repo/ktweak).

![](/images/posts/magisk.png)
