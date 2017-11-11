---
layout: post
title: "Variables en Ruby"
date: 2017-10-07
excerpt: "Tercer capítulo del curso de Ruby"
tags: [ruby]
---

En este tercer capítulo del curso de Ruby aprenderás a declarar y manipular variables sin preocuparte del tipo de dato (en ruby no es necesario especificar que la variable x es de tipo entero, por ejemplo), también verás algunas prácticas utilizadas a la hora de inicializar una variable y por último, verás lo que son las **constantes** y en qué se diferencian a una variable.

# Variables

Una variable corresponde a un **espacio de almacenamiento** en memoria RAM, la cual está definida por 4 elementos: nombre, dirección, tipo y valor. En palabras más simples, corresponde a un "almacen" de datos dentro de la memoria.

Ejemplo:

{% highlight ruby %}
nombre = "Nicolas"
{% endhighlight %}

En el ejemplo anterior tenemos que el nombre de la variable es `nombre`, luego se encuentra el operador `=`, cuyo significado es que en la variable se guardará el dato que se encuentra a la derecha de dicho signo (en este caso el nombre **"Nicolas"**).

Otros ejemplos:

{% highlight ruby %}
edad = 24
peso = 66.45
tutor = "Nicolas"
{% endhighlight %}

Una cosa muy importante es que en ruby **no necesitas especificar el tipo de dato de una variable**, ya que el mismo intérprete se encarga de deducir si el valor es un entero, decimal, cadena, etc.

A continuación tienes un mini programa que guarda una cadena de texto en una variable y luego la muestra por pantalla:

{% highlight ruby %}
nombre = "Nicolas"
puts nombre
{% endhighlight %}

Otra cosa importante en ruby es que puedes cambiar el tipo de dato de una variable sin problemas y cuando quieras. Por ejemplo:

{% highlight ruby %}
variable = "Nicolas"
puts variable
variable = 20
puts variable
{% endhighlight %}

Si conoces algún otro lenguaje de programación como C o Java, debes tener bien claro que **no puedes utilizar palabras reservadas de dichos lenguajes como nombres de variables**. Si eres un principiante en el mundo de la programación, las palabras reservadas (tales como `def`, `and`, `if` y `true`, entre otras) por lo general toman un color azul.

# Inicialización de variables

A la hora de trabajar con variables, puede darse el caso que contengan más de una palabra. Por lo general, se suele separar cada palabra con un guión bajo, por ejemplo:

{% highlight ruby %}
nombre_del_tutor = "Nicolas"
{% endhighlight %}

Esta práctica se conoce como **Snake case** (recibe este nombre ya que todo está en un mismo nivel y separado por guiones). Existe otra práctica que hace uso de las mayúsculas (ignorando el guión bajo) y se conoce como **Camel case**, por ejemplo:

{% highlight ruby %}
nombreDelTutor = "Nicolas"
{% endhighlight %}

Para efectos prácticos conviene utilizar **Snake case**.

# Constantes

Una constante se diferencia a una variable en que **no cambia durante la ejecución de un programa**. Para definir una constante en ruby, basta con que la primera letra del nombre, o todas, sean mayúsculas. Por ejemplo:

{% highlight ruby %}
Pi = 3.14
Nombre_del_tutor = "Nicolas"
NUM = 1
{% endhighlight %}

# Comentarios

Este apartado se aleja un poco de lo que son las variables y constantes. Sin embargo, el escribir comentarios es una buena práctica a la hora de programar, ya sea en Ruby o cualquier otro lenguaje de programación ya que logramos documentar, por ejemplo, un pequeño fragmento de código o un complejo proyecto, entre otros.

Escribir comentarios agiliza la curva de aprendizaje en cualquier proyecto (y en el lenguaje que sea), ya que cuando dejamos de tener interacción con un lenguaje de programación, es normal que olvidemos las instrucciones que éste ejecuta, por lo que gracias a los comentarios logramos tener una idea más clara de lo que ejecuta el código que estamos analizando.

Para escribir comentarios en Ruby sólo debes utilizar el símbolo `#` al principio del texto que escribirás, por ejemplo:

{% highlight ruby %}
# Esto es un comentario en Ruby
puts "Estoy aprendiendo Ruby"
{% endhighlight %}

En muchas ocasiones los comentarios serán muy largos (de varias líneas), por lo que, como ocurre en muchos otros lenguajes, existen los comentarios multilínea o de bloque, por ejemplo:

{% highlight ruby %}
=begin
Esto es un
comentario
de muchas
líneas
=end

puts "Hola Mundo"
{% endhighlight %}

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/instalacion-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/){: .btn .btn-success} |
