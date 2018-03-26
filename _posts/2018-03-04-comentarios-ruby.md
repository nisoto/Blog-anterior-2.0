---
layout: post
title: "Variables en Ruby"
date: 2018-03-04
excerpt: "Capítulo N°4 del curso de Ruby"
tags: [ruby]
---

# Variables

Una **variable** es el nombre de una ubicación de almacenamiento para un valor. Es llamada _variable_ porque la información almacenada en esa ubicación puede ser modificada cuando el programa es ejecutado.

Para asignar un valor a una variable, se utiliza el signo igual (`=`). Por ejemplo:

{% highlight ruby %}
x = 8
{% endhighlight %}

Esta declaración de asignación declara una variable llamada `x` y le otorga el valor 8. El signo _"igual"_ es llamado el operador de asignación.

Posteriormente podemos utilizar el nombre de la variable para acceder a su valor. Por ejemplo, para desplegar el valor almacenado en la variable, podemos utilizar `puts` o `print` y referirnos al nombre de la variable:

{% highlight ruby %}
x = 8
puts x
# outputs 8
{% endhighlight %}

**Nota:** los nombres de las variables pueden consistir de caracteres alfanuméricos y el caracter de guión bajo (`_`), pero no pueden comenzar con una letra mayúscula.

# Constantes

Las variables que comienzan con una letra mayúscula son llamadas **constantes**. El valor de una _variable constante_ no puede ser modificado una vez que haya sido asignado. Por ejemplo:

{% highlight ruby %}
MyNum = 42
MyNum = 8
# warning: already initialized constant MyNum
{% endhighlight %}

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/comentarios-ruby/){: .btn .btn-info} | [Volver](https://nisoto.github.io/curso-ruby/){: .btn .btn-info} | [>](https://nisoto.github.io/entrada-salida-ruby/){: .btn .btn-info} |
