---
layout: post
title: "Comentarios en Ruby"
date: 2018-03-03
excerpt: "Capítulo N°3 del curso de Ruby"
tags: [ruby]
---

# Comentarios

Los comentarios son líneas de anotaciones dentro del código Ruby que son ignoradas en tiempo de ejecución del programa.

En Ruby, el **símbolo de numeral** (#) es utilizado para crear un comentario de una sola línea. Por ejemplo:

{% highlight ruby %}
# imprimiendo un texto
puts "Hola Ruby"
{% endhighlight %}

Todo lo que sigue al símbolo de numeral en esa línea es ignorado cuando el programa es ejecutado.

# Comentarios de varias líneas

También puedes crear comentarios de varias líneas. Todo lo que esté entre las palabras reservadas `begin` y `end` es considerado un comentario:

{% highlight ruby %}
=begin
Este comentario
posee varias
lineas
=end
puts "Hola"
{% endhighlight %}

**Nota:** añadir comentarios a tu código es una buena práctica. Facilita un entendimiento claro del código para ti y para otros que lo lean.

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/hola-ruby/){: .btn .btn-info} | [Volver](https://nisoto.github.io/curso-ruby/){: .btn .btn-info} | [>](https://nisoto.github.io/variables-ruby/){: .btn .btn-info} |
