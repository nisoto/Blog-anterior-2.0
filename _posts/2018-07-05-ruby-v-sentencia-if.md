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

# Declaraciones else

Un bloque `else` en una expresión `if` contiene código que es invocado cuando la condición `if` evalúa a **falso**. Por ejemplo:

{% highlight ruby %}
age = 15
if age > 18
    puts "Bienvenido"
else
    puts "Eres menor de edad"
end
# salida: "Eres menor de edad"
{% endhighlight %}

**Nota:** la palabra clave `end` sólo es necesaria para la declaración `if`, ya que el bloque `else` es parte de la expresión `if`.

# Declaraciones elsif

El bloque `elsif` (abreviado para `else if`) es útil cuando quieres evaluar varias condiciones. Una serie de expresiones `if elsif` pueden tener un bloque `else` final, el cual es invocado si ninguna de las expresiones `if` o `elsif` son verdaderas. Por ejemplo:

{% highlight ruby %}
num = 8
if num == 3
    puts "El numero es igual a 3"
elsif num == 10
    puts "El numero es igual a 10"
elsif num == 7
    puts "El numero es igual a 7"
else
    puts "Numero no encontrado"
end
# salida: "Numero no encontrado"
{% endhighlight %}

**Nota:** cuando un bloque `elsif` es ejecutado, se sale de la expresión `if` completa.

# Declaraciones unless

La expresión `unless` es lo opuesto de una expresión `if`, ya que ejecutará código cuando un condicional es **falso**. Por ejemplo:

{% highlight ruby %}
a = 42
unless a < 10
    puts "Si"
else
    puts "No"
end
# salida: "Yes"
{% endhighlight %}

Puedes utilizar un bloque `else` con el `unless`, tal y como se detalla en el ejemplo anterior. La palabra clave `end` también es requerida para cerrar el bloque.

Los modificadores `if` y `unless` también pueden ser utilizados para ejecutar código, es decir:

{% highlight ruby %}
a = 42
puts "Si" if a > 10 
puts "Si" unless a < 10
{% endhighlight %}

El còdigo antes del `if` es ejecutado sólo si la condición evalúa a **verdadero**, mientras que el código antes del `unless` es ejecutado sólo si la condición es **falsa**.

**Nota:** como puedes ver, el código Ruby es mucho más corto y fácil de leer, haciéndolo un lenguaje de programación muy intuitivo.

## Ejercicio

Debes crear un programa que determine si el número `43` es par o impar.

Respuesta:

{% highlight ruby %}
num = 43
if num%2 == 0
    puts "El numero es par"
else
    puts "El numero es impar"
end
{% endhighlight %}

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/ruby-iv-otros-operadores/){: .btn .btn-info} | [Volver](https://nisoto.github.io/blog/){: .btn .btn-info} | [>](https://nisoto.github.io/blog/){: .btn .btn-info} |
