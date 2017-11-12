---
layout: post
title: "Entrada y salida de datos en Ruby"
date: 2017-10-09
excerpt: "Quinto capítulo del curso de Ruby"
tags: [ruby]
---

En este quinto capítulo del curso de Ruby verás la entrada y salida de información en lenguaje Ruby, donde aprenderás a ingresar, por ejemplo, un número o cadena desde teclado para manipularlo a tu antojo.

# Entrada

A lo largo del curso hemos estado utilizando el método `puts`, por lo que seguramente te preguntarás ¿Qué diablos es eso? La respuesta es muy simple, `puts` hace referencia a imprimir o desplegar texto por pantalla, por ejemplo:

{% highlight ruby %}
puts "Hola, esto es un texto"
{% endhighlight %}

Es importante destacar que el método puts es equivalente a:

{% highlight ruby %}
put String
{% endhighlight %}

Lo que significa, como se dijo anteriormente, **imprimir texto**.

# Salida

También tenemos el método `gets`, con el cual podemos recibir un texto desde el teclado, por ejemplo:

{% highlight ruby %}
nombre = gets
{% endhighlight %}

Tal como ocurrre con `puts`, el método gets es equivalente a:

{% highlight ruby %}
get String
{% endhighlight %}

# Primer programa

Ahora que hemos visto los métodos `puts` y `gets`, el siguiente fragmento de código corresponde a un programa que pregunta tu nombre y luego te saluda:

{% highlight ruby %}
puts "Hola, como te llamas?"
name = gets
puts "Mucho gusto #{name}, como estas?"
{% endhighlight %}

Si ejecutas el código anterior, te darás cuenta que en la última cadena de texto ("Mucho gusto Nicolas, como estas?") habrá un salto de línea después de tu nombre. Esto se debe básicamente a que cuando ingresas el texto, también se guardará el salto de línea (al presionar la tecla `ENTER` o `INTRO` de tu teclado). Para solucionar este problema existe el método `chomp`, el cual elimina el último caracter de la cadena que ingreses desde teclado.

Si utilizamos el método `chomp` en el ejemplo anterior, quedaría de la siguiente forma:

{% highlight ruby %}
puts "Hola, como te llamas?"
name = gets.chomp
puts "Mucho gusto #{name}, como estas?"
{% endhighlight %}

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/datos-elementales-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/){: .btn .btn-success} |
