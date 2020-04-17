---
layout: post
title: "Ruby on Rails IV: Ruby"
date: 2020-04-12
excerpt: "Capítulo N°4 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ¿Qué es Ruby?

Ruby es un **lenguaje de programación** creado por el programador japonés Yukihiro "Matz" Matsumoto cuyas características principales son las siguientes:

* **Es interpretado**, es decir, no existe un compilador ya que parte del instalador incluye un intérprete que lee línea por línea las instrucciones del lenguaje de programación y las va ejecutando.
* **Sin puntos y coma**, lo que reduce la cantidad de tiempo que uno a veces invierte buscando errores de sintáxis, como ocurre habitualmente en lenguajes como C++ y Java, entre otros.
* Es de **tipado dinámico**, por lo que no necesitas definir cual es el tipo de una variable.
* **Todo es un objeto**, lo que ofrece flexibilidad al lenguaje.
* Es **muy productivo** ya que puedes terminar proyectos más rápidos que con otros lenguajes.
* Puedes **reescribir el lenguaje**, es decir, puedes abrir una clase del lenguaje y agregar tus propios métodos (reescribir el lenguaje), tal como se detalló un poco más arriba.

## 2. Consola Interactiva de Ruby (IRB)

Una vez instalado **Ruby** en nuestra computadora, sólo debemos escribir `irb` en la terminal para ingresar a la **Consola Interactiva** (IRB por sus siglas en inglés) que incluye este lenguaje:

```
$ irb
irb(main):001:0>
```

Todo lo que escribamos luego de este comando será evaluado como **código de Ruby**. Partiremos escribiendo nuestro primer programa, el clásico **"Hola Mundo"**:

```
irb(main):001:0> puts "Hola Mundo"
Hola Mundo
=> nil
irb(main):002:0>
```

La **Consola Interactiva** de Ruby será bastante útil si estás dando tus primeros pasos en este lenguaje o bien, si quieres realizar algunas pruebas, pero a la hora de desarrollar programas más elaborados, lo recomendable es utilizar algún editor de código como **Atom** y luego ejecutar dicho programa a través de la terminal de acuerdo a la siguiente nomenclatura:

```
$ ruby hola_mundo.rb
```

Donde `hola_mundo` corresponde al nombre del programa y `.rb` es la extensión de **Ruby** (así como `.c` lo es para el lenguaje **C** y `.py` lo es para **Python**).

## 3. Variables

Una variable corresponde a un espacio de memoria que puede cambiar su contenido a lo largo de la ejecución de un programa.

``` rb
name = "Nicolas"
age = 23
pi = 3.14
```

A diferencia de otros lenguajes de programación, en Ruby no es necesario especificar el tipo de dato de una variable ya que el intérprete deduce cual es su tipo a partir del valor.

Si queremos imprimir el valor de una variable (como `name`) debemos utilizar la palabra reservada `puts` (tal como lo hicimos en el apartado anterior al escribir el clásico `"Hola Mundo"`), la cual nos sirve para desplegar por pantalla una cadena, número y/o un objeto.

``` rb
name = "Nicolas"
puts name
```

Si ahora quisiéramos cambiar el valor de la variable `name` a `25`, esto sería totalmente válido (algo que en muchos otros lenguajes resultaría en un error), ya que como se especificó anteriormente, Ruby deduce el tipo de dato. Por ejemplo:

``` rb
name = "Nicolas"
puts name
name = 25
puts name
name = 3.14
puts name
```

El programa mostrará por pantalla la cadena `"Nicolas"`, luego el número entero `25` y por último el número con decimales `3.14`.

Existen algunas restricciones a considerar a la hora de trabajar con variables:
* A una variable no debes darle nombres de palabras reservadas del lenguaje (tales como `new`, `def`, `if`, etc.). Si eres un principiante en el mundo de la programación, las palabras reservadas en Ruby por lo general toman un color distinto al blanco.
* No debes colocar la primera letra del nombre de una variable con mayúsculas porque en ese caso estaríamos hablando de una **Constante** (es decir, su valor no podrá ser modificado durante la ejecución de un programa).
* El nombre de una variable no puede comenzar con un número ya que esto generaría un error.

### 3.1. Números

Dentro de lo que son los números tenemos dos importantes tipos o grupos:

1. Enteros (`int`): No tienen punto decimal.
2. Punto Flotante (`float`): Contienen al menos un dígito después del punto.

Algunos ejemplos:

``` rb
x = 20        # Entero
y = 20.0      # Punto flotante
z = 365       # Entero
w = 3.141592  # Punto flotante
```

Tal como sucede en otros lenguajes, si ejecutamos una operación aritmética entre 2 números enteros, el resultado será un entero, y lo mismo ocurrirá para los números de punto flotante:

``` rb
x = 10
y = 3
puts x / y  # 3

a = 10.0
b = 3.0
puts a / b  # 3.3333333333333335
```

No olvidemos que en Ruby los números no son primitivos, **¡son objetos!**; por lo que como todo objeto, éstos tienen métodos asociados. Algunos de los más utilizados son los siguientes:

``` rb
# Determina el valor absoluto de un número
a = -10
puts a.abs  # 10

# Determina si un número es par o impar
b = 3
puts b.even?  # FALSE (ya que se trata de un número impar)

# Determina el sucesor de un número
c = 2
puts c.next  # 3

# Convierte un número entero a punto flotante
d = 10
puts d.to_f  # 10.0

# Convierte un número de punto flotante a entero
e = 12.53
puts e.to_i  # 12 (retorna la parte entera mediante truncamiento)
```

Existen muchos métodos que podemos utilizar para trabajar con los números, los cuales podremos ver en detalle si añadimos `.methods()` a una variable que almacene un número (cualquiera sea su tipo).

### 3.2. Cadenas

Una cadena o `string` corresponde a un conjunto de caracteres:

``` rb
cadena = "Hola mundo"
nombre = 'Nicolas'
```

Podemos utilizar tanto las comillas dobles como las simples, aunque generalmente se utilizan las primeras (el porqué se especifica más adelante).

Por lo general, a la hora de trabajar con cadenas vamos a querer tener variables que incluyan el resultado de una operación, para ello existen 2 formas:

#### 1. Concatenación

``` rb
nombre = "Nicolas"
puts "Hola " + nombre
```

#### 2. Interpolación

``` rb
nombre = "Nicolas"
puts "Hola #{nombre}"  # Lo que se encuentra dentro de las llaves se evalúa como código de Ruby
```

Al igual que los números, las cadenas también poseen métodos ya que son objetos. Algunos de los más utilizados son los siguientes:

``` rb
# Determina la cantidad de caracteres de una cadena
cadena = "Esto es una cadena en Ruby"
puts cadena.length  # 26

# Convierte los caracteres de una cadena a mayúsculas
nombre = "nicolas"
puts nombre.upcase  # "NICOLAS"

# Convierte los caracteres de una cadena a minúsculas
nombre = "NICOLAS"
puts nombre.downcase  # "nicolas"

# Convierte la primera letra de una cadena a mayúscula
nombre = "nicolas"
puts nombre.capitalize  # "Nicolas"

# Convierte una cadena a número entero
numero = "2"
puts numero.to_i  # 2

# Convierte una cadena a número de punto flotante
num = "3"
puts num.to_f  # 3.0

# Convierte un número (entero o de punto flotante) a cadena
a = 1
b = 2.0
puts a.to_s  # "1"
puts b.to_s  # "2.0"

# Determina si una cadena contiene a la subcadena "Ruby"
cadena = "Esto es una cadena en Ruby"
puts cadena.include? "Ruby"  # TRUE

# Invierte una cadena
nombre = "nicolas"
puts nombre.reverse  # "salocin"
```

Al igual que con los números, para las cadenas también tenemos un sin fín de métodos a utilizar los cuales podremos ver en detalle si añadimos `.methods()` a una variable que almacene un `string`.

Si utilizamos tildes lo más probable es que tengamos problemas a la hora de ejecutar un programa, por lo que para solucionar este inconveniente debemos agregar al principio del código lo siguiente:

``` rb
# encoding: utf-8
```

#### 3.2.1. Caracteres no imprimibles

``` rb
\n  # Salto de línea
\t  # Tabulación
```

Es importante mencionar que para los caracteres no imprimibles debemos utilizar doble comilla, ya que de esta forma se interpretan, mientras que las comillas simples se conservan. Con el ejemplo a continuación podemos notar la diferencia:

``` rb
irb(main):001:0> puts "Hola\n\n\n"
Hola


=> nil
irb(main):002:0> puts 'Hola\n\n\n'
Hola\n\n\n
=> nil
```

#### 3.2.2. Métodos peligrosos

Un método es peligroso cuando **modifica** al objeto sobre el que se está trabajando, por ejemplo:

``` rb
cadena = "nicolas"
cadena.upcase!  # El signo de exclamación modifica al objeto
puts cadena
```

Al imprimir la variable `cadena`, nos daremos cuenta que el texto ha sido modificado.

## 4. Entrada y Salida de datos

Ya hemos visto en más de una ocasión la palabra reservada o método `puts`, la cual hace referencia a imprimir o desplegar texto por pantalla:

``` rb
puts "Hola, esto es una cadena de caracteres"
```

Para recibir un texto desde el teclado, existe el método `gets`:

``` rb
nombre = gets
```

### 4.1. Primer programa

Con lo aprendido hasta ahora, crearemos un programa que pregunta nuestro nombre y luego nos saluda:

``` rb
# encoding: utf-8
puts "Hola, ¿Cómo te llamas?"
name = gets
puts "Mucho gusto #{name}, ¿Cómo estás?"  # Mucho gusto Nicolas
                                          # , ¿Cómo estás?
```

Si ejecutamos este código, nos daremos cuenta que en la última línea (saludo) habrá un salto de línea después de nuestro nombre. Esto se debe a que cuando ingresamos el texto, el método `gets` también guarda el salto de línea (cuando presionamos la tecla `ENTER` o `INTRO` del teclado). Solucionar este inconveniente es bastante sencillo si utilizamos el método `chomp`, el cual elimina el último caracter de la cadena que estamos ingresando desde teclado.

Si agregamos el método `chomp` al ejemplo anterior, quedaría algo como lo siguiente:

``` rb
# encoding: utf-8
puts "Hola, ¿Cómo te llamas?"
name = gets.chomp
puts "Mucho gusto #{name}, ¿Cómo estás?"  # Mucho gusto Nicolas, ¿Cómo estás?
```

### 4.2. Uso de comentarios

Escribir comentarios a nuestro programa es una buena práctica, cualquiera sea el lenguaje de programación que estemos utilizando. En Ruby podemos realizar comentarios de una sola línea:

``` rb
# Esto es un comentario en Ruby
puts " Estoy aprendiendo Ruby"
```

O de varias líneas (también llamados de multilínea o de bloque):

``` rb
=begin
Esto es un
comentario
de varias
líneas
=end
puts "Hola Mundo"
```

## 5. Operadores

### 5.1. Atirméticos

``` rb
a = 10
b = 5

# Suma
puts a + b  # 15

# Resta
puts a - b  # 5

# Multiplicación
puts a * b  # 50

# División
puts a / b  # 2

# Módulo
puts a % b  # 0

# Potencia
puts a ** b  # 100000
```

### 5.2. Comparación

``` rb
a = 10
b = 5
c = 5

# Mayor que
puts a > b  # TRUE

# Menor que
puts a < b  # FALSE

# Mayor o igual que
puts b >= c  # TRUE

# Menor o igual que
puts b <= c  # TRUE

# Es igual que
puts b == c  # TRUE

# Es distinto que
puts a != b  # TRUE

# Comparador Combinado
puts a <=> b  # 1 (el valor de la izquierda es mayor que el de la derecha)
puts b <=> a  # -1 (el valor de la derecha es mayor que el de la izquierda)
puts b <=> c  # 0 (tanto el valor de la izquierda como el de la derecha son iguales)

# Comparador del tipo de dato
d = 1
e = 1.0
puts d.eql?(e)  # FALSE (verifica que tengan el mismo valor y además el mismo tipo de dato)

# Comparador del identificador único (object_id)
f = "Hola"
g = "Hola"
puts f.equal?(g)  # FALSE (cada variable posee un identificador único en Ruby)
puts f.object_id  # 45289900
puts g.object_id  # 44136620
```

### 5.3. Lógicos

Hola.

### 5.4. Orden de precedencia

El **orden de precedencia** de todos los operadores (aritméticos, de comparación y lógicos) es el siguiente:

1. Potencia
2. Multiplicación, División y Módulo
3. Suma y Resta

Si tuvieramos operadores en el mismo nivel (una multiplicación con una división por ejemplo), Ruby en ese caso realiza la evaluación de izquierda a derecha. Una forma de **alterar** la precedencia es utilizar **paréntesis**.

## 10. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°3](https://nisoto.github.io/rails-iii-instalacion/){: .btn .btn-info} | [Lección N°5 >](https://nisoto.github.io/rails-v-git-en-detalle/){: .btn .btn-info} |
