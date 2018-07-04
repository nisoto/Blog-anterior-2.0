---
layout: post
title: "Ruby III: Strings"
date: 2018-07-03
excerpt: "Capítulo N°3 del curso de Ruby"
tags: [ruby]
---

# Strings

Tal y como se mencionó en las lecciones anteriores, una `string` (cadena de caracteres) corresponde a un texto entre comillas simples o dobles.

Es importante destacar que algunos caracteres no pueden ser incluidos directamente. Por ejemplo, las comillas simples no pueden ser directamente incluidas en una `string` de comillas simples, porque esto designaría el final de la cadena. Caracteres como estos pueden ser incluidos en una `string` utilizando una **secuencia de escape**, la cual se indica con una **barra invertida** (`\`):

{% highlight ruby %}
text = 'Ruby\'s divertido'
puts text
# salida: Ruby's divertido
{% endhighlight %}

Una `string` formada con comillas dobles también puede incluir la secuencia de escape `\n`, la cual representa una nueva línea:

{% highlight ruby %}
text = "Hola \n Ruby es divertido"
puts text
# salida: Hola
#          Ruby es divertido
{% endhighlight %}

**Nota:** sólo las secuencias de escape `\'` y `\\` pueden ser utilizadas con `strings` de comillas simples.

# Interpolación de cadenas

Puedes incrustar cualquier expresión de Ruby dentro de una `string` de comillas dobles utilizando `#{}`, tal cual como lo haces con nombres de variables:

{% highlight ruby %}
a = 5
b = 2
puts "La suma es #{a+b}"
# salida: La suma es 7
{% endhighlight %}

Ruby evalúa los marcadores y los reemplaza por valores.
