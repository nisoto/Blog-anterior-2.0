---
layout: post
title: "Operadores en Ruby"
date: 2017-10-10
excerpt: "Sexto capítulo del curso de Ruby"
tags: [ruby]
---

En este sexto capítulo del curso de Ruby verás...

# Operadores aritméticos

Estos operadores **manipulan** datos numéricos (tanto enteros como reales):

* Suma (`+`)
* Resta (`-`)
* Multiplicación (`*`)
* División (`/`)
* Módulo (`%`): Devuelve el **resto de una división** entera.
* Potencia (`**`)

Ejemplo:

{% highlight ruby %}
x=10
y=5
puts x+y #El resultado será 15
puts x-y #El resultado será 5
puts x*y #El resultado será 50
puts x/y #El resultado será 2
puts x%y #El resultado será 0
puts x**y #Es lo mismo que x^y, el resultado será 100.000
{% endhighlight %}
