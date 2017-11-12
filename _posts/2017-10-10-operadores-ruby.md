---
layout: post
title: "Operadores en Ruby"
date: 2017-10-10
excerpt: "Sexto capítulo del curso de Ruby"
tags: [ruby]
---

En este sexto capítulo del curso de Ruby verás...

# Operadores aritméticos

Estos operadores **manipulan** datos numéricos (tanto enteros como reales):

* Suma (`+`)
* Resta (`-`)
* Multiplicación (`*`)
* División (`/`)
* Módulo (`%`): Devuelve el **resto de una división** entera.
* Potencia (`**`)

Ejemplo:

{% highlight ruby %}
x=10
y=5
puts x+y   #El resultado será 15
puts x-y   #El resultado será 5
puts x*y   #El resultado será 50
puts x/y   #El resultado será 2
puts x%y   #El resultado será 0
puts x**y  #Es lo mismo que x^y, el resultado será 100.000
{% endhighlight %}

Con los operadores vistos hasta el momento ya podemos crear un programa más elaborado como determinar si un número es par o impar:

{% highlight ruby %}
num = gets.chomp
num = numero.to_i #Lo convertimos a entero
resto = num%2
if resto==0
    puts "#{num} es par"
else
    puts "#{num} ingresado es impar"
end
{% endhighlight %}

Si al dividir el número ingresado por 2 el resto es `0`, significa que estamos ante un número par (sentencia `if`). En caso contrario (`else`), el resto será distinto de `0`.

Si no te quedó muy claro la finalidad de las palabras reservadas `if` y `else` no te preocupes ya que más adelante lo veremos con detalle.

## Orden de precedencia

Un factor clave a la hora de manejar los operadores artirméticos es la precedencia que éstos tienen. Por ejemplo:

{% highlight ruby %}
20 - 10 * 2
{% endhighlight %}

En Ruby, el orden de precedencia de los operadores aritméticos es el siguiente:

1. Potencia
2. Multiplicación, División y Módulo
3. Suma y Resta

Por lo tanto, la expresión anterior da como resultado `0`.

¿Qué pasaría si ahora tenemos algo como lo siguiente?:

{% highlight ruby %}
10 * 2 / 5
{% endhighlight %}

¿Cuál operador se ejecutará primero? Para casos como este se evalúa la expresión de **izquierda a derecha**, es decir, primero se ejecutará la multiplicación y luego la división, dando como resultado el valor `4`.

## Uso de paréntesis

Una forma de **alterar la precedencia** es utilizar parántesis en las expresiones. Por ejemplo:

{% highlight ruby %}
(20 - 10) * 2
{% endhighlight %}

Considerando el orden de precedencia, el resultado debería ser `0`; sin embargo, el uso de paréntesis altera la precedencia, causando que la resta pase a primer plano. Dicho lo anterior, el resultado de la expresión será `20`.

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/entrada-salida-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/){: .btn .btn-success} |
