---
layout: post
title: "Tipos de datos elementales en Ruby"
date: 2017-10-08
excerpt: "Cuarto capítulo del curso de Ruby"
tags: [ruby]
---

En este cuarto capítulo del curso de Ruby verás los distintos tipos de datos elementales, los cuales se clasifican principalmente en **números** y **cadenas**. Aprenderás a trabajar con ellas, es decir, a inicializarlas y manipularlas a lo largo de la ejecución de un programa y por último, conocerás algunos de los métodos más utilizados, tanto para los números como para las cadenas (recuerda que en Ruby todo es un objeto, y todo objeto tiene sus métodos).

# Números

En Ruby tenemos 2 grupos generales de números: los **Enteros** (`int`) y los de **Coma flotante** (`float`). Por ejemplo:

{% highlight ruby %}
entero = 20
punto_flotante = 20.0
{% endhighlight %}

Tal como sucede en otros lenguajes, si ejecutas una operación entre 2 números enteros, el resultado será un entero; y ocurrirá lo mismo para los números de punto flotante. Veamos el siguiente fragmento de código (en IRB):

{% highlight ruby %}
irb(main):001:0> 12/5
=> 2
irb(main):002:0> 12.0/5.0
=> 2.4
{% endhighlight %}

Otra cosa importante es que en Ruby los números no son primitivos, **¡son objetos!**; así que como todo objeto tiene métodos, los números no son la excepción. Veamos algunos de los métodos más utilizados:

{% highlight ruby %}
# Convertir un número entero a coma flotante
10.to_f

# Convertir un número en coma flotante a entero
12.23.to_i #Retornará la parte entera, en este caso 12

# Determinar el valor absoluto
-10.abs

# Verificar si un número es par
3.even? #En este caso retornará false ya que 3 es impar

# Retornar el número siguiente (sucesor)
2.next
{% endhighlight %}

Como te habrás dado cuenta, existe un sin fin de métodos para los números, por lo que te recomiendo que revises la documentación de Ruby si quieres conocerlos todos o bien, ejecutes la siguiente línea de código (en IRB):

{% highlight ruby %}
10.methods
{% endhighlight %}

Puedes escribir cualquier número mientras sea de tipo entero.

# Cadenas

Una cadena o **string** corresponde a un conjunto de caracteres (recuerda que un caracter puede ser una letra, un espacio o incluso un signo). Se inicializan de la siguiente manera:

{% highlight ruby %}
cadena = "Hola mundo"
cadena2 = 'Hola mundo'
{% endhighlight %}

Como pudiste notar, puedes utilizar tanto las comillas dobles como las simples (aunque generalmente se utilizan las comillas dobles).

Antes de continuar, debes tener claro que una variable es un identificador que se le asigna a un objeto. En los ejemplos anteriores, la cadena es un objeto de la clase String, por lo tanto, contamos con los distintos métodos existentes para dicha clase (los cuales se detallan más adelante).

A la hora de manipular cadenas, por lo general querrás tener variables que incluyan el resultado de una operación. Para ello existen 2 formas:

## Concatenación

Veamos el siguiente ejemplo:

{% highlight ruby %}
nombre = "Nicolas"
puts "Hola " + nombre
{% endhighlight %}

## Interpolación

Tomando el ejemplo anterior:

{% highlight ruby %}
nombre = "Nicolas"
puts "Hola #{nombre}"
{% endhighlight %}

Cabe destacar que lo que está dentro de las llaves se evalúa como **código de Ruby**.

Al igual que los números, las cadenas también son métodos. Veamos algunos de los métodos más utilizados:

{% highlight ruby %}
# Determinar la cantidad de caracteres de una cadena
"nicolas".length

# Convertir una cadena a mayúscula
"nicolas".upcase

# Convertir una cadena a minúscula
"NICOLAS".downcase

# Convertir la primera letra de una cadena a mayúscula
"nicolas".capitalize
{% endhighlight %}

Tal vez te parezca raro que los métodos detallados anteriormente no tengan el respectivo paréntesis al final. Esto se debe a que en Ruby no es obligatorio usar paréntesis, pues solo se recomienda cuando el método recibe parámetros, por ejemplo:

{% highlight ruby %}
cadena = "Mi primera cadena en Ruby"
puts cadena.slice(3,7)
{% endhighlight %}

El método `slice` crea una subcadena, donde el primer parámetro corresponde al inicio de la subcadena (desde donde queremos comenzar) y el segundo parámetro corresponde a la cantidad de caracteres (en adelante) que queremos mostrar de la cadena.

Debido a que existen muchos métodos para las cadenas, y tal como se hizo más arriba para los números, conviene ejecutar la siguiente línea de código (en IRB):

{% highlight ruby %}
"".methods
{% endhighlight %}

Para mayor información, te recomiendo que revises la documentación de [Ruby](https://www.ruby-lang.org/es/documentation/).

Una cosa importante es que si utilizas tildes, puede que tengas problemas a la hora de ejecutar tus programas, por lo que te recomiendo agregar, al principio de tu código, la siguiente línea:

{% highlight ruby %}
# encoding: utf-8
{% endhighlight %}

## Caracteres no imprimibles

Los caracteres no imprimibles son símbolos creados por las tabulaciones, saltos de línea (enter), etc., que no aparecen al imprimir una cadena o un número, por ejemplo.

{% highlight ruby %}
\n #Salto de línea
\t #Tabulación
{% endhighlight %}

Es importante mencionar que para los caracteres no imprimibles se debe utilizar doble comilla, ya que de esta forma se interpretan, mientras que si utilizamos comillas simples, éstos se conservan. Veamos el siguiente ejemplo para que notes la diferencia:

{% highlight ruby %}
irb(main):001:0> puts "Hola\n\n\n"
Hola


=> nil
irb(main):002:0> puts 'Hola\n\n\n'
Hola\n\n\n
=> nil
{% endhighlight %}

Además de los métodos vistos anteriormente para las cadenas, existen otros que pueden ser de gran utilidad:

{% highlight ruby %}
# Convertir una cadena a número entero
"2".to_i

# Convertir una cadena a número de punto flotante
"3".to_f

# Convertir un número (entero o de punto flotante) a cadena
1.to_s

# Retorna True o False dependiendo si la cadena está vacía o no
"nicolas".empty?

# Determina si la cadena contiene a la subcadena "Ruby" (retorna True o False)
"Esto es una cadena en Ruby".include? 'Ruby'

# Invertir una cadena
"nicolas".reverse
{% endhighlight %}

¿Qué pasaría ahora si intentamos convertir la cadena `"1asdf"` a número? Mediante los métodos `to_i` o `to_f`, lo que haría Ruby sería tomar la cadena y considerar los números que se encuentran al principio, ignorando todo lo demás. Por ejemplo:

{% highlight ruby %}
irb(main):001:0> "4asdf".to_i
=> 4
irb(main):002:0> "4qwerty".to_f
=> 4.0
irb(main):003:0> "345asdf".to_i
=> 345
{% endhighlight %}

¿Y si ahora tuviéramos la cadena `"asd1fgh"`? A diferencia del ejemplo anterior (donde el número está al principio), si la cadena que queremos convertir no comienza con un número, el resultado será un `0`. Por ejemplo:

{% highlight ruby %}
irb(main):001:0> "asd1fgh".to_i
=> 0
irb(main):002:0> "asd1fgh".to_f
=> 0.0
{% endhighlight %}

## Métodos peligrosos

Un método es peligroso cuando modifica al objeto sobre el que se está trabajando. Consideremos el siguiente ejemnplo:

{% highlight ruby %}
cadena = "nicolas"
cadena.upcase! # El signo de exclamación modifica al objeto
puts cadena
{% endhighlight %}

Al imprimir la variable `cadena`, nos daremos cuenta que el texto se ha modificado.

|     |     |
|----:|:----|
| [<](https://nisoto.github.io/variables-ruby/){: .btn .btn-success} | [>](https://nisoto.github.io/entrada-salida-ruby/){: .btn .btn-success} |
