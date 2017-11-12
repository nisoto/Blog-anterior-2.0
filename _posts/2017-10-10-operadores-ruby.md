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

Si al dividir el número ingresado por 2 el resto es `0`, significa que estamos ante un número par (sentencia `if`). En caso contrario, el resto será distinto de `0`.

Si no te quedó muy claro la finalidad de las palabras reservadas `if` y `else` no te preocupes ya que más adelante lo veremos con detalle.
