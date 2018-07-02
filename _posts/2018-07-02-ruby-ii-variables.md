---
layout: post
title: "Ruby II: Variables"
date: 2018-07-02
excerpt: "Capítulo N°2 del curso de Ruby"
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
# salida: 8
{% endhighlight %}

**Nota:** los nombres de las variables pueden consistir de caracteres alfanuméricos y el caracter de guión bajo (`_`), pero no pueden comenzar con una letra mayúscula.

# Constantes

Las variables que comienzan con una letra mayúscula son llamadas **constantes**. El valor de una _variable constante_ no puede ser modificado una vez que haya sido asignado. Por ejemplo:

{% highlight ruby %}
MyNum = 42
# si intentamos cambiar el valor se produce una advertencia
MyNum = 8
# warning: already initialized constant MyNum
{% endhighlight %}

# Tipos de datos

Todas las variables en Ruby pueden ser de todos los **tipos de datos**. Ruby determina automáticamente el tipo de dato por el valor asociado a la variable. Por ejemplo:

{% highlight ruby %}
x = 42      # integer
y = 1.58    # floating point value
z = "Hola"  # string
{% endhighlight %}

Puedes reasignar un valor diferente a una variable en cualquier momento.

Para insertar el valor de una variable dentro de una `string` de comillas dobles (una `string` es una secuencia de caracteres, tal como "Hola"), utiliza el símbolo `#` y llaves con el nombre de la variable. Por ejemplo:

{% highlight ruby %}
age = 42
puts "El tiene #{age} años de edad"
# salida: "El tiene 42 años de edad"
{% endhighlight %}

## Ejercicio

Debes crear un programa que inserte tu nombre dentro de la string "Hola, TuNombre".

Respuesta:

{% highlight ruby %}
name = "Nicolas"
puts "Hola #{name}"
{% endhighlight %}

# Haciendo matemáticas

Las matemáticas son una parte importante de la programación. Ruby soporta los siguientes **operadores aritméticos**:

{% highlight ruby %}
x = 5
y = 2

# Suma
puts x+y
# salida: 7

# Resta
puts x-y
# salida: 3

# Multiplicacion
puts x*y
# salida: 10

# Division
puts x/y
# salida: 2
{% endhighlight %}

Cuando divides dos valores enteros, el resultado será un **entero**, como se muestra en el ejemplo anterior. Si deseas tener un resultado de punto flotante, un operando debe ser un valor de punto flotante:

{% highlight ruby %}
x = 5.0
y = 2
puts x/y 
# salida: 2.5
{% endhighlight %}

# Operador Módulo

El operador **módulo**, representado por el símbolo de porcentaje (`%`), representa el resto de una operación de división. Por ejemplo:

{% highlight ruby %}
x = 9
y = 5
puts x%y
# salida: 4
{% endhighlight %}

9 dividido entre 5 es 1, con un resto de 4.

# Operador exponente

El operador **exponente** está representado por `**` para elevar un número a una potencia y realizar la exponenciación. Por ejemplo:

{% highlight ruby %}
a = 2
b = 5
puts a**b
# salida: 32
{% endhighlight %}

El resultado es 32 ya que `2*2*2*2*2 = 32`.

**Nota:** todos los operadores también pueden ser utilizados con valores de punto flotante.

# Operadores abreviados de asignación

Todos los operadores aritméticos tienen formas abreviadas correspondientes para la asignación. Por ejemplo, `a = a + 8` puede ser escrito como `a += 8`, lo mismo para otros operadores:

{% highlight ruby %}
x += y   # x = x+y
x -= y   # x = x-y
x *= y   # x = x*y
x /= y   # x = x/y
x %= y   # x = x%y
x **= y  # x = x**y
{% endhighlight %}

Estos son llamados **operadores de auto-asignación**, ya que ejecutan una asignación y una operación aritmética al mismo tiempo.

# Asignación paralela

Ruby también soporta la asignación paralela de variables. Esto permite que varias variables sean inicializadas con una sola línea de código. Por ejemplo:

{% highlight ruby %}
x = 10
y = 20
z = 30
{% endhighlight %}

Puede ser inicializado más rápidamente utilizando asignación paralela:

{% highlight ruby %}
x, y, z = 10, 20, 30
{% endhighlight %}

**Nota:** la asignación paralela es también útil para intercambiar los valores almacenados en dos variables, es decir:

{% highlight ruby %}
a, b = b, a
{% endhighlight %}

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/ruby-i-introduccion/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/matematicas-ruby/){: .btn .btn-info} |
