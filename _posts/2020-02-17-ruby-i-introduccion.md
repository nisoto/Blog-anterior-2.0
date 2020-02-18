---
layout: post
title: "Curso de Ruby I: Introducción"
date: 2020-02-17
excerpt: "Capítulo N°1 del curso de Ruby"
tags: [ruby]
---

# 1. ¿Qué es Ruby?

Ruby es un **lenguaje de programación** creado por el programador japonés Yukihiro “Matz” Matsumoto en 1995, el cual está inspirado en Lisp, Perl, Smalltalk, Eiffel y Ada.

## Características

* Interpretado
* No hay puntos y comas
* Tipado dinámico (no es necesario indicar el tipo de dato)
* Todo es un **objeto**, lo que permite una mayor flexibilidad

## Ventajas

* Productividad
* Puedes reescribir el lenguaje
* Es muy expresivo ya que prefiere el inglés a la puntuación
* Inspiró la creación de otros lenguajes

## Uso de Ruby

* Aplicaciones Web (Ruby on Rails)
* Utilidades de la terminal
* Aplicaciones móviles nativas (Rubymotion)
* Interfaces gráficas

## Empresas que utilizan Ruby

* Basecamp
* Github
* Airbnb
* Heroku
* Tumblr

**Nota:** Ruby tiene un lema **No te repitas** (Don't Repeat Yourself o DRY), el cual consiste en escribir menos código y que el mantenimiento sea más práctico.

# 2. Variables

Una **variable** es un espacio de almacenamiento en la memoria que puede cambiar su contenido a lo largo de la ejecucion de un programa.

``` ruby
nombre = "Nicolas"
```

Donde:
* `nombre`: Nombre de la variable
* `=`: Operador de asignación
* `"Nicolas"`: Valor (puede ser un número, una cadena, un arreglo, etc.)

Las variables no definen tipo (el intérprete lo deduce).

``` ruby
edad = 26
cadena = "Mensaje"
puts cadena #imprime la palabra "Mensaje"
cadena = 30
puts cadena #imprime el nuevo valor asignado (30)
```

Una **Constante**, a diferencia de una Variable, no cambia su valor a lo largo de la ejecución del programa.

``` ruby
Nombre = "Nicolas"
```

La primera letra del nombre de una constante **siempre** debe ser con mayúsculas.

|     |     |
|:----|----:|
| [< Inicio](https://nisoto.github.io/blog/){: .btn .btn-info} | [Instalación >](https://nisoto.github.io/curso-ruby-ii-instalacion/){: .btn .btn-info} |
