---
layout: post
title: "Ruby on Rails IV: Ruby"
date: 2020-04-12
excerpt: "Capítulo N°4 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ¿Qué es Ruby?

Ruby es un **lenguaje de programación** creado por el programador japonés Yukihiro "Matz" Matsumoto cuyas características principales son las siguientes:

* **Es interpretado**, es decir, no existe un compilador ya que parte del instalador incluye un intérprete que lee línea por línea las instrucciones del lenguaje de programación y las va ejecutando.
* **Sin puntos y coma**, lo que reduce la cantidad de tiempo que uno a veces invierte buscando errores de sintáxis, como ocurre habitualmente en lenguajes como C++ y Java, entre otros.
* Es de **tipado dinámico**, por lo que no necesitas definir cual es el tipo de una variable.
* **Todo es un objeto**, lo que ofrece flexibilidad al lenguaje.
* Es **muy productivo** ya que puedes terminar proyectos más rápidos que con otros lenguajes.
* Puedes **reescribir el lenguaje**, es decir, puedes abrir una clase del lenguaje y agregar tus propios métodos (reescribir el lenguaje), tal como se detalló un poco más arriba.

## 2. Consola Interactiva de Ruby (IRB)

Una vez instalado **Ruby** en nuestra computadora, sólo debemos escribir `irb` en la terminal para ingresar a la **Consola Interactiva** (IRB por sus siglas en inglés) que incluye este lenguaje:

```
$ irb
irb(main):001:0>
```

Todo lo que escribamos luego de este comando será evaluado como **código de Ruby**. Partiremos escribiendo nuestro primer programa, el clásico **"Hola Mundo"**:

```
irb(main):001:0> puts "Hola Mundo"
Hola Mundo
=> nil
irb(main):002:0>
```

La **Consola Interactiva** de Ruby será bastante útil si estás dando tus primeros pasos en este lenguaje o bien, si quieres realizar algunas pruebas, pero a la hora de desarrollar programas más elaborados, lo recomendable es utilizar algún editor de código como **Atom** y luego ejecutar dicho programa a través de la terminal de acuerdo a la siguiente nomenclatura:

```
$ ruby hola_mundo.rb
```

Donde `hola_mundo` corresponde al nombre del programa y `.rb` es la extensión de **Ruby** (así como `.c` lo es para el lenguaje **C** y `.py` lo es para **Python**).

|     |     |
|:----|----:|
| [< Lección N°3](https://nisoto.github.io/rails-iii-instalacion/){: .btn .btn-info} | [Lección N°5 >](https://nisoto.github.io/rails-v-git-en-detalle/){: .btn .btn-info} |
