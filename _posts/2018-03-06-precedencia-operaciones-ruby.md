---
layout: post
title: "Precedencia de operaciones en Ruby"
date: 2018-03-06
excerpt: "Capítulo N°6 del curso de Ruby"
tags: [ruby]
---

# Precedencia de operaciones

Ruby evalúa una expresión matemática utilizando un orden en las operaciones que está basado en la precedencia de los operadores. La exponenciación tiene mayor precedencia seguida de la multiplicación, división y el módulo de izquierda a derecha, y la adición y sustracción de izquierda a derecha:

1. Potencia
2. Multiplicación, División y Módulo
3. Suma y Resta

Consideremos los siguientes ejemplos:

{% highlight ruby %}
a = 20 - 10 * 2
puts a
# salida: 0

b = 10 * 2 / 5
puts b
# salida: 4
{% endhighlight %}

Una forma de **alterar la precedencia** es utilizar parántesis en las expresiones, por ejemplo:

{% highlight ruby %}
x = (3 + 2) * 4
puts x
# salida: 20

y = (20 + 10) / 2
puts y
# salida: 15
{% endhighlight %}

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/matematicas-ruby/){: .btn .btn-info} | [Volver](https://nisoto.github.io/curso-ruby/){: .btn .btn-info} | [>](https://nisoto.github.io/){: .btn .btn-info} |
