---
layout: post
title: "Tipos de datos elementales en Ruby"
date: 2017-10-08
excerpt: "Cuarto capítulo del curso de Ruby"
tags: [ruby]
---

En este cuarto capítulo del curso de Ruby verás los distintos tipos de datos elementales, los cuales se clasifican principalmente en **números** y **cadenas**. Aprenderás a trabajar con ellas, es decir, a inicializarlas y manipularlas a lo largo de la ejecución de un programa y por último, conocerás algunos de los métodos más utilizados, tanto para los números como para las cadenas (recuerda que en Ruby todo es un objeto, y todo objeto tiene sus métodos).

# Números

En Ruby tenemos 2 grupos generales de números: los **Enteros** (`int`) y los de **Coma flotante** (`float`). Por ejemplo:

{% highlight ruby %}
entero = 20
punto_flotante = 20.0
{% endhighlight %}

Tal como sucede en otros lenguajes, si ejecutas una operación entre 2 números enteros, el resultado será un entero; y ocurrirá lo mismo para los números de punto flotante. Veamos el siguiente fragmento de código (en IRB):

{% highlight ruby %}
irb(main):001:0> 12/5
=> 2
irb(main):002:0> 12.0/5.0
=> 2.4
{% endhighlight %}

Otra cosa importante es que en Ruby los números no son primitivos, **¡son objetos!**; así que como todo objeto tiene métodos, los números no son la excepción. Veamos algunos de los métodos más utilizados:

{% highlight ruby %}
# Convertir un número entero a coma flotante
10.to_f

# Convertir un número en coma flotante a entero
12.23.to_i #Retornará la parte entera, en este caso 12

# Determinar el valor absoluto
-10.abs

# Verificar si un número es par
3.even? #En este caso retornará false ya que 3 es impar

# Retornar el número siguiente (sucesor)
2.next
{% endhighlight %}

Como te habrás dado cuenta, existe un sin fin de métodos para los números, por lo que te recomiendo que revises la documentación de Ruby si quieres conocerlos todos o bien, ejecutes la siguiente línea de código (en IRB):

{% highlight ruby %}
10.methods
{% endhighlight %}

Puedes escribir cualquier número mientras sea de tipo entero.

# Cadenas

Una cadena o **string** corresponde a un conjunto de caracteres (recuerda que un caracter puede ser una letra, un espacio o incluso un signo). Se inicializan de la siguiente manera:

{% highlight ruby %}
cadena = "Hola mundo"
cadena2 = 'Hola mundo'
{% endhighlight %}

Como pudiste notar, puedes utilizar tanto las comillas dobles como las simples (aunque generalmente se utilizan las comillas dobles).

Antes de continuar, debes tener claro que una variable es un identificador que se le asigna a un objeto. En los ejemplos anteriores, la cadena es un objeto de la clase String, por lo tanto, contamos con los distintos métodos existentes para dicha clase (los cuales se detallan más adelante).

A la hora de manipular cadenas, por lo general querrás tener variables que incluyan el resultado de una operación. Para ello existen 2 formas:

## Concatenación

Veamos el siguiente ejemplo:

{% highlight ruby %}
nombre = "Nicolas"
puts "Hola " + nombre
{% endhighlight %}

## Interpolación

Tomando el ejemplo anterior:

{% highlight ruby %}
nombre = "Nicolas"
puts "Hola #{nombre}"
{% endhighlight %}

Cabe destacar que lo que está dentro de las llaves se evalúa como **código de Ruby**.

Al igual que los números, las cadenas también son métodos. Veamos algunos de los métodos más utilizados:

{% highlight ruby %}
# Determinar la cantidad de caracteres de una cadena
"nicolas".length

# Convertir una cadena a mayúscula
"nicolas".upcase

# Convertir una cadena a minúscula
"NICOLAS".downcase

# Convertir la primera letra de una cadena a mayúscula
"nicolas".capitalize
{% endhighlight %}

Tal vez te parezca raro que los métodos detallados anteriormente no tengan el respectivo paréntesis al final. Esto se debe a que en Ruby no es obligatorio usar paréntesis, pues solo se recomienda cuando el método recibe parámetros, por ejemplo:

{% highlight ruby %}
cadena = "Mi primera cadena en Ruby"
puts cadena.slice(3,7)
{% endhighlight %}

El método `slice` crea una subcadena, donde el primer parámetro corresponde al inicio de la subcadena (desde donde queremos comenzar) y el segundo parámetro corresponde a la cantidad de caracteres en adelante que queremos mostrar de la cadena.

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/variables-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/){: .btn .btn-success} |
