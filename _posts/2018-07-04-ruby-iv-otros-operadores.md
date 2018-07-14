---
layout: post
title: "Ruby IV: Otros operadores"
date: 2018-07-04
excerpt: "Capítulo N°4 del curso de Ruby"
tags: [ruby]
---

# Booleanos

En Ruby, existen dos valores Booleanos: **true** (verdadero) y *false* (falso). Por ejemplo:

{% highlight ruby %}
isOnline = true
userIsAdmin = false
{% endhighlight %}

Otro valor que encontrarás usualmente es **`nil`**, el cual representa la ausencia de valor (vacío).

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

Otro operador de comparación, el operador **distinto que** (`!=`), evalúa a verdadero si los operandos comparados no son iguales, y falso si lo son, es decir:

{% highlight ruby %}
a = 8
b = 7

puts a != b # true
{% endhighlight %}

Ruby también tiene operadores que determinan si un valor es **mayor que** o **menor que** otro. Estos operadores son `>` y `<` respectivamente. De forma similar, los operadores **mayor o igual que** y **menor o igual que** son `>=` y `<=`. Por ejemplo:

{% highlight ruby %}
puts 12 > 8    # true

puts 5 < 2     # false

puts 5 >= 5.0  # true

puts 3 <= 6    # true
{% endhighlight %}

También está el método `.eql?`, el cual resulta en verdadero sólo si ambos argumentos tienen el **mismo tipo e igual valores**. Por ejemplo:

{% highlight ruby %}
puts 3 == 3.0     # true

puts 3.eql?(3.0)  # false
{% endhighlight %}

`3.eql?(3.0)` es **falso** porque `3` es un entero y `3.0` es un flotante.

**Nota:** los operadores mayor que y menor que también pueden ser utilizados para comparar `strings` lexicográficamente (el orden alfabético de las palabras basado en el orden alfabético de las letras que las componen).

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/ruby-iii-strings/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/ruby-v-sentencia-if/){: .btn .btn-info} |
