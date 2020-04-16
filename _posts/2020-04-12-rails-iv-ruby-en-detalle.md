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

## 3. Variables

Una variable corresponde a un espacio de memoria que puede cambiar su contenido a lo largo de la ejecución de un programa.

``` rb
name = "Nicolas"
age = 23
pi = 3.14
```

A diferencia de otros lenguajes de programación, en Ruby no es necesario especificar el tipo de dato de una variable ya que el intérprete deduce cual es su tipo a partir del valor.

Si queremos imprimir el valor de una variable (como `name`) debemos utilizar la palabra reservada `puts` (tal como lo hicimos en el apartado anterior al escribir el clásico `"Hola Mundo"`), la cual nos sirve para desplegar por pantalla una cadena, número y/o un objeto.

``` rb
name = "Nicolas"
puts name
```

Si ahora quisiéramos cambiar el valor de la variable `name` a `25`, esto sería totalmente válido (algo que en muchos otros lenguajes resultaría en un error), ya que como se especificó anteriormente, Ruby deduce el tipo de dato. Por ejemplo:

``` rb
name = "Nicolas"
puts name
name = 25
puts name
name = 3.14
puts name
```

El programa mostrará por pantalla la cadena `"Nicolas"`, luego el número entero `25` y por último el número con decimales `3.14`.

Existen algunas restricciones a considerar a la hora de trabajar con variables:
* A una variable no debes darle nombres de palabras reservadas del lenguaje (tales como `new`, `def`, `if`, etc.). Si eres un principiante en el mundo de la programación, las palabras reservadas en Ruby por lo general toman un color distinto al blanco.
* No debes colocar la primera letra del nombre de una variable con mayúsculas porque en ese caso estaríamos hablando de una **Constante** (es decir, su valor no podrá ser modificado durante la ejecución de un programa).
* El nombre de una variable no puede comenzar con un número ya que esto generaría un error.

### 3.1. Números

Dentro de lo que son los números tenemos dos importantes tipos o grupos:

1. Enteros (`int`): No tienen punto decimal.
2. Punto Flotante (`float`): Contienen al menos un dígito después del punto.

Algunos ejemplos:

``` rb
x = 20        # Entero
y = 20.0      # Punto flotante
z = 365       # Entero
w = 3.141592  # Punto flotante
```

Tal como sucede en otros lenguajes, si ejecutamos una operación aritmética entre 2 números enteros, el resultado será un entero, y lo mismo ocurrirá para los números de punto flotante:

``` rb
x = 10
y = 3
puts x / y  # 3

a = 10.0
b = 3.0
puts a / b  # 3.3333333333333335
```

No olvidemos que en Ruby los números no son primitivos, **¡son objetos!**; por lo que como todo objeto, éstos tienen métodos asociados. Algunos de los más utilizados son los siguientes:

``` rb
# Determina el valor absoluto de un número
a = -10
puts a.abs  # 10

# Determina si un número es par o impar
b = 3
puts b.even?  # FALSE
# Imprimirá por pantalla TRUE si se trata de un número par o FALSE en caso contrario

# Determina el sucesor de un número
c = 2
puts c.next  # 3

# Convierte un número entero a punto flotante
d = 10
puts d.to_f  # 10.0

# Convierte un número de punto flotante a entero
e = 12.53
puts e.to_i  # 12 (retorna la parte entera)
```

### 3.2. Cadenas

Hola.

## 10. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°3](https://nisoto.github.io/rails-iii-instalacion/){: .btn .btn-info} | [Lección N°5 >](https://nisoto.github.io/rails-v-git-en-detalle/){: .btn .btn-info} |
