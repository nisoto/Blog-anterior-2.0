---
layout: post
title: "Ruby I: Introducción y primer programa"
date: 2018-03-01
excerpt: "Capítulo N°1 del curso de Ruby"
tags: [ruby]
---

# ¡Bienvenido a Ruby!

Ruby es un **lenguaje de programación** de propósito general, dinámico y orientado a objetos.

Está considerado dentro de los 10 mejores lenguajes de programación a nivel mundial. Mucho de su crecimiento es atribuido a la popularidad del software escrito en Ruby, particularmente el Framework para desarrollo web **Ruby on Rails**.

Citando a su creador, **Yukihiro "Matz" Matsumoto**: _"Ruby es simple en apariencia, pero es muy complejo internamente, tal como nuestro cuerpo humano"_.

Matsumoto ha dicho que Ruby está diseñado para la productividad del programador y para que sea divertido, siguiendo los principios de diseño correcto de interfaz de usuario.

En Ruby, todo (incluso un simple número) es un **objeto**. Aprenderás más acerca de objetos en los siguientes capítulos.

**Nota:** Ruby también es completamente gratuito. No solo libre de cargos, sino también libre para ser usado, copiado, modificado y distribuido.

# Primer programa

Vamos a crear nuestro primer programa en Ruby, el clásico **"Hola Mundo"**. Para esto, utilizaremos el método incorporado `puts`.

{% highlight ruby %}
puts "Hola Mundo"
{% endhighlight %}

Este código desplegará el texto **"Hola Mundo"** en la pantalla.

**Nota:** todos los valores de texto (strings) deben ser encerrados entre comillas simples o dobles.

## Ejercicio Nro. 1

Debes crear un programa que imprima por pantalla la frase "Ruby es divertido".

Respuesta:

{% highlight ruby %}
puts "Ruby es divertido"
{% endhighlight %}

# Método Print

Otro método que puede ser utilizado para desplegar salida en la pantalla es `print`. Por ejemplo:

{% highlight ruby %}
print "Hola Mundo"
{% endhighlight %}

Este código despliega la misma salida que antes, con la excepción de que `puts` añade automáticamente una nueva línea (o salto de línea) después de la salida, mientras que `print` no lo hace. Por ejemplo:

{% highlight ruby %}
puts "Hola"
print "aqui"
print "Ruby"
{% endhighlight %}

Resultado:

{% highlight ruby %}
Hola
aquiRuby
{% endhighlight %}

# Comentarios

Los comentarios son líneas de anotaciones dentro del código Ruby que son ignoradas en tiempo de ejecución del programa.

En Ruby, el **símbolo de numeral** (#) es utilizado para crear un comentario de una sola línea. Por ejemplo:

{% highlight ruby %}
# imprimiendo un texto
puts "Hola Ruby"
{% endhighlight %}

Todo lo que sigue al símbolo de numeral en esa línea es ignorado cuando el programa es ejecutado.

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/blog/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/hola-ruby/){: .btn .btn-info} |
