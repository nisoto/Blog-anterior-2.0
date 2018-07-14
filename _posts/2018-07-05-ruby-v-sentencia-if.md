---
layout: post
title: "Ruby V: Sentencia if-else"
date: 2018-07-05
excerpt: "Capítulo N°5 del curso de Ruby"
tags: [ruby]
---

# Declaraciones if

Puedes utilizar una expresión `if` para ejecutar código cuando se cumpla una cierta condición. Si una expresión condicional evalúa a **verdadero**, el código `if` es ejecutado y, en otro caso, el código es ignorado. Por ejemplo:

{% highlight ruby %}
a = 42
if a > 7
    puts "Si"
end
# salida: "Si"
{% endhighlight %}

La condición `a > 7` es evaluada. Cuando es **verdadera**, las declaraciones dentro del `if` son ejecutadas y el programa despliega "Si". Puedes tener varias declaraciones dentro de una sola expresión `if`.

**Nota:** la palabra clave `end` es requerida para indicar el final del `if`.

Las expresiones `if` pueden ser anidadas una dentro de otra, esto significa que el `if` más interno es el código del externo. Esta es una forma de ver si varias condiciones son satisfechas.

{% highlight ruby %}
num = 16
if num > 7
    puts "El numero es mayor que 7"
    if num < 42
        puts "El numero es mayor que 7 menor que 42"
    end
end
# salida: El numero es mayor que 7
#         El numero es mayor que 7 menor que 42
{% endhighlight %}

Ten presente que una vez que una condición `if` falle, se saldrá del bloque completo.

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/ruby-iv-otros-operadores/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/blog/){: .btn .btn-info} |
