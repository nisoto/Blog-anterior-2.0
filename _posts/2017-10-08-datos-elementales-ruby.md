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

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/variables-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/){: .btn .btn-success} |
