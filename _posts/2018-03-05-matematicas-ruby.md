---
layout: post
title: "Matemáticas en Ruby"
date: 2018-03-05
excerpt: "Capítulo N°5 del curso de Ruby"
tags: [ruby]
---

# Haciendo matemáticas

Las matemáticas son una parte importante de la programación. Ruby soporta los siguientes **operadores aritméticos**:

{% highlight ruby %}
x = 5
y = 2

# Suma
puts x+y
# outputs 7

# Resta
puts x-y
# outputs 3

# Multiplicacion
puts x*y
# outputs 10

# Division
puts x/y
# outputs 2
{% endhighlight %}

Cuando divides dos valores enteros, el resultado será un **entero**, como se muestra en el ejemplo anterior. Si deseas tener un resultado de punto flotante, un operando debe ser un valor de punto flotante:

{% highlight ruby %}
x = 5.0
y = 2
puts x/y 
# outputs 2.5
{% endhighlight %}

# Operador Módulo

El operador **módulo**, representado por el símbolo de porcentaje (`%`), representa el resto de una operación de división. Por ejemplo:

{% highlight ruby %}
x = 9
y = 5
puts x%y
# outputs 4
{% endhighlight %}

9 dividido entre 5 es 1, con un resto de 4.

# Operador exponente

El operador **exponente** está representado por `**` para elevar un número a una potencia y realizar la exponenciación. Por ejemplo:

{% highlight ruby %}
a = 2
b = 5
puts a**b
# outputs 32
{% endhighlight %}

El resultado es 32 ya que `2*2*2*2*2 = 32`.

**Nota:** todos los operadores también pueden ser utilizados con valores de punto flotante.

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/variables-ruby/){: .btn .btn-info} | [Volver](https://nisoto.github.io/curso-ruby/){: .btn .btn-info} | [>](https://nisoto.github.io/operadores-ruby/){: .btn .btn-info} |
