---
layout: post
title: "Ruby III: Strings y entrada/salida de datos"
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
# salida: "La suma es 7"
{% endhighlight %}

Ruby evalúa los marcadores y los reemplaza por valores.

# Concatenación

Las `strings` pueden ser unidas utilizando el signo `+`  en un proceso llamado **concatenación** (unión). Cuando concatenamos cadenas, no importa si han sido creadas con comillas simples o dobles:

{% highlight ruby %}
a = "Hola "
b = 'Ruby'
puts a+b
# salida: "Hola Ruby"
{% endhighlight %}

**Nota:** aunque las `strings` contengan números, ellas serán unidas como cadenas en lugar de ser sumadas como enteros. Añadir una `string` a un número produce un error, porque aunque pueden verse similares, son dos entidades completamente diferentes: `"1"` es una `string`, mientras que `1` es un entero.

# Repitiendo una cadena

Las `strings` pueden ser repetidas utilizando el símbolo `*` y un valor entero. El orden entre la cadena y el entero **importa**: el `string` tiene que aparecer primero. Por ejemplo:

{% highlight ruby %}
a = "abc"
puts a*3
# salida: "abcabcabc"

puts '5'*4
# salida: 5555
{% endhighlight %}

Las `strings` no pueden ser multiplicadas por otras `strings`.

# Input

Para obtener la entrada del usuario en Ruby, utilizamos el método `gets`, el cual retorna lo que el usuario escribe como una `string`. Para almacenar la entrada para su posterior uso, podemos asignar el valor de retorno a una variable. Por ejemplo:

{% highlight ruby %}
x = gets
puts x
{% endhighlight %}

`gets` obtiene una línea de texto, incluyendo el salto de línea al final. Si no quieres incluir el salto de línea, se debe utilizar el método `chomp`:

{% highlight ruby %}
puts "Ingresa tu nombre: "
name = gets.chomp
puts "Bienvenido #{name}"
{% endhighlight %}

**Nota:** el valor de la entrada es una `string`. Para convertirla a un **entero**, puedes utilizar el método `gets.to_i`.

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/ruby-ii-variables/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/blog/){: .btn .btn-info} |