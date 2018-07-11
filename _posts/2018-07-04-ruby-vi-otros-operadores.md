---
layout: post
title: "Ruby VI: Otros operadores"
date: 2018-07-04
excerpt: "Capítulo N°4 del curso de Ruby"
tags: [ruby]
---

# Booleanos

En Ruby, existen dos valores Booleanos: **true** (verdadero) y *false* (falso):

{% highlight ruby %}
isOnline = true
userIsAdmin = false
{% endhighlight %}

Otro valor que encontrarás usualmente es `nil`, el cual representa la ausencia de valor (vacío).

Si intentas evaluar un valor distinto que **true** o **false** como un Booleano, Ruby automáticamente lo tratará como un Booleano. Cuando esto ocurre, un valor no-Booleano que es evaluado como verdadero es llamado **`truthy`**, y un no-Booleano que evalúa a falso es llamado **`falsey`**.

En Ruby sólo **`false`** y **`nil`** son `falsey`. Todo lo demás es `truthy` (incluso el `0`).

**Nota:** sólo **true** y **false** son Booleanos. `nil` no es un Booleano, `0` no es un Booleano y la `string` "Hola" tampoco lo es. Sin embargo, en un contexto donde se espera un Booleano, Ruby los evalúa como Booleano (`truthy` y `falsey`).

# Comparación

Una comparación Booleana utilizando el operador `==` retornará **true** cuando los dos operandos son iguales, y **false** cuando no lo son, es decir:

{% highlight ruby %}
a = 5
b = 8

puts a == b # false

puts a == 5 # true
{% endhighlight %}

Ten cuidado de no confundir **asignación** (=) con **comparación** (==).
