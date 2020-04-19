---
layout: post
title: "Ruby on Rails IV: Ruby básico"
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
puts cadena  # "NICOLAS"
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

``` rb
a = 10
b = 5
c = 8

# Y (and)
puts (a > b) && (b < c)  # TRUE
puts (a > b) && (b > c)  # FALSE

# O (or)
puts (a > b) || (b < c)  # TRUE
puts (a > b) || (b > c)  # TRUE

# Negación (not)
puts !true  # FALSE
puts !false  # TRUE
```

### 5.4. Orden de precedencia

El **orden de precedencia** de todos los operadores (aritméticos, de comparación y lógicos) es el siguiente:

1. Potencia (`**`)
2. Negación (`!`)
3. Multiplicación (`*`), División (`/`), Módulo (`%`)
4. Suma (`+`), Resta (`-`)
5. Mayor que (`>`), Menor que (`<`), Mayor o igual que (`>=`), Menor o igual que (`<=`)
6. Igual que (`==`), Combinado (`<=>`), Distinto que (`!=`)
7. Y (`&&`)
8. O (`||`)
9. Asignación (`=`)
10. Negación (`not`)
11. Y (`and`), O (`or`)

Si tuvieramos operadores en el mismo nivel (una multiplicación con una división por ejemplo), Ruby en ese caso realiza la evaluación de izquierda a derecha. Una forma de **alterar** la precedencia es utilizar **paréntesis**.

## 6. Condiciones

### 6.1. Condición `if`

#### 1. `if`

``` rb
a = 10
b = 5
if a > b
  puts "#{a} es mayor que #{b}"
end
```

Lo anterior también puede ser escrito de la siguiente manera:

``` rb
a = 10
b = 5
puts "#{a} es mayor que #{b}" if a > b
```

Esto funcionará correctamente si la sentencia dentro del `if` es de **una sola línea**.

#### 2. `if-else`

Tal como en el ejemplo anterior, imaginemos que leemos 2 números enteros desde teclado y queremos compararlos:

``` rb
a = gets.chomp.to_i
b = gets.chomp.to_i
if a > b
  puts "#{a} es mayor que #{b}"
else
  puts "#{a} es menor que #{b}"
end
```

Si la condición dentro del `if` es **falsa**, entonces se ejecutará lo que hay en `else`.

#### 3. `if-elsif-else`

Tomando nuevamente el primer ejemplo de este apartado ¿Qué pasaría si los números leídos desde teclado son iguales? La palabra reservada `elsif` nos ayuda en este caso:

``` rb
a = gets.chomp.to_i
b = gets.chomp.to_i
if a > b
  puts "#{a} es mayor que #{b}"
elsif a == b
  puts "#{a} es igual que #{b}"
else
  puts "#{a} es menor que #{b}"
end
```

#### 4. `unless`

Funciona como el inverso de `if` ya que ejecutará la(s) sentencia(s) siempre y cuando la condición sea **falsa**.

``` rb
a = 10
b = 5
unless a < b
  puts "Hola Mundo"
end
# Hola Mundo
```

Que también puede se puede escribir como:

``` rb
a = 10
b = 5
puts "Hola Mundo" unless a < b  # Hola Mundo
```

### 6.2. Operador ternario

El operador ternario no es nada más que otra forma de utilizar `if-else` de manera más expresiva:

``` rb
# encoding: utf-8

# Leeremos un número desde teclado y determinaremos si es par o impar
num = gets.chomp.to_i

# if-else en una sola línea
puts (if num % 2 == 0 then "El número ingresado es par" else "El número ingresado es impar" end)

# if-else utilizando el operador ternario
puts num % 2 == 0 ? "El número ingresado es par" : "El número ingresado es impar"
```

### 6.3. Sentencia `case`

Esta sentencia funciona de la misma forma que `elsif`:

``` rb
# encoding: utf-8

# Leeremos una calificación por teclado y determinaremos si el alumno aprueba o reprueba
print "Ingresa tu calificación: "
calificacion = gets.chomp.to_i

# Utilizando if-elsif-else
if calificacion == 7
  puts "¡Excelente!"
elsif calificacion == 6
  puts "¡Muy bien! Vas por buen camino"
elsif calificacion == 5
  puts "Bien, pero aún puedes mejorar"
elsif calificacion == 4
  puts "Sabemos que lo puedes hacer mejor"
else
  puts "Estás reprobado"
end

# Utilizando case
case calificacion
when 7
  puts "¡Excelente!"
when 6
  puts "¡Muy bien! Vas por buen camino"
when 5
  puts "Bien, pero aún puedes mejorar"
when 4
  puts "Sabemos que lo puedes hacer mejor"
else
  puts "Estás reprobado"
end
```

## 7. Arreglos

Un **arreglo** (array en inglés) corresponde a una **estructura de datos** en la que podemos almacenar elementos cualquiera sea su tipo de dato.

``` rb
arreglo = [3,'Perro',true]  # Inicializamos un array con 3 casillas, donde cada una posee un elemento de distinto tipo
arreglo_dos = Array.new(5)  # Inicializamos un array con 5 casillas vacias (nil)
arreglo_tres = %w[1 40 'cadena']  # Inicializamos un array de 3 casillas (con %w evitamos el uso de comas)
```

Acceder a las **casillas** de un arreglo es bastante sencillo:

``` rb
arreglo = [3,'Perro',true]
puts arreglo[0]  # 3
puts arreglo[2]  # TRUE
puts arreglo[5]  # nil (no existe esa posición)
```

También es importante destacar que en Ruby, los arreglos no tienen una dimensión (tamaño) definida, por lo que en cualquier momento podemos agregar uno o más elementos:

``` rb
arreglo = [3,'Perro',true]
arreglo[3] = 3.14
puts arreglo  # [3,'Perro',true,3.14]
arreglo << 'Hola'  # Otra forma de agregar un elemento
puts arreglo  # [3,'Perro',true,3.14,'Hola']
```

### 7.1. Iterando un arreglo

Podemos recorrer los elementos de un arreglo de muchas maneras. Uno de los métodos más utilizados es `each`:

``` rb
# encoding: utf-8

# Determinaremos
# El promedio de todas las calificaciones de un curso
# Cuál es la mayor nota y en qué posición se encuentra
calificaciones = %w[7 4 5 6 3 6 2]
# Tener en cuenta que %w almacena todos los elementos de un arreglo como string

# Promedio
suma = 0
total = calificacion.length
calificaciones.each do |calificacion|
  suma += calificacion.to_f  # Convertimos las calificaciones a float
end
puts "El promedio de las calificaciones del curso es #{suma / total}"  # 4.714285714285714

# Mayor nota
mayor = -1
pos = -1
aux = 0
calificaciones.each_with_index do |calificacion,posicion|
  aux = calificacion.to_i
  if aux > mayor
    mayor = aux
    pos = posicion
  end
end
puts "La mayor calificación es #{mayor}, ubicada en la posición #{pos} del arreglo"
```

### 7.2. Operaciones en arreglos

Existen varios métodos que nos permitirán trabajar los arreglos, algunos de los más conocidos son:

``` rb
# encoding: utf-8
arreglo = [1,1,2,2,3,4,5,6,7]

# Multiplicación (join)
puts arreglo * 2  # [1,1,2,2,3,4,5,6,7,1,1,2,2,3,4,5,6,7]
puts arreglo * 3  # [1,1,2,2,3,4,5,6,7,1,1,2,2,3,4,5,6,7,1,1,2,2,3,4,5,6,7]
puts arreglo * " - "  # 1 - 1 - 2 - 2 - 3 - 4 - 5 - 6 - 7
puts arreglo * ", "  # 1, 1, 2, 2, 3, 4, 5, 6, 7
puts arreglo.join(", ")  # 1, 1, 2, 2, 3, 4, 5, 6, 7
# Este operador convierte el arreglo en una cadena

# Ordenamiento
puts arreglo.sort  # [1,1,2,2,3,4,5,6,7]
puts arreglo.sort.reverse  # [7,6,5,4,3,2,2,1,1]

# Búsqueda de un elemento
puts arreglo.include?(6)  # TRUE
puts arreglo.include?(9)  # FALSE

# Otras operaciones:
# Retorna el primer elemento
puts arreglo.first  # 1
# Retorna el último elemento
puts arreglo.last  # 7
# Retorna el arreglo eliminando los valores repetidos
puts arreglo.uniq  # [1,2,3,4,5,6,7]
# Rtorna un elemento del arreglo de manera aleatoria
puts arreglo.sample  # 3
```

### 7.3. Rangos

Los **Rangos** nos sirven para expresar una secuencia, ya sea de números, caracteres, etc.

``` rb
# encoding: utf-8
# Imprimir los primeros 10 números naturales

# Utilizando un arreglo
numeros = [1,2,3,4,5,6,7,8,9,10]
numeros.each do |numero|
  puts numero
end

# Utilizando rangos
(1..10).each do |numero|
  puts numero
end
```

Algunos de los métodos más utilizados en los rangos son los siguientes:

``` rb
# encoding: utf-8

# Imprime los primeros 20 números naturales de dos en dos
(1..20).step(2).each do |numero|
  puts numero
end
# 1 3 5 7 9 11 13 15 17 19

# Determina el valor mínimo de un rango
puts (0..20).min  # 0

# Determina el valor máximo de un rango
puts (0..20).max  # 20

# Convierte un rango en un arreglo
puts (0..20).to_a  # [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]
```

### 7.4. Otros iteradores

Además de `each`, existen más iteradores tales como `while`, `until` y `do-while`.

``` rb
# encoding: utf-8

num_magico = 20
# Adivinaremos el número mágico utilizando distintos iteradores

# Utilizando while (mientras que)
print "Adivina el número mágico: "
num_usuario = gets.chomp.to_i
while num_usuario != num_magico
  print "Incorrecto, adivina otra vez: "
  num_usuario = gets.chomp.to_i
end
puts "Adivinaste, felicidades"

# Utilizando until (inverso de while)
print "Adivina el número mágico: "
num_usuario = gets.chomp.to_i
until num_usuario == num_magico
  print "Incorrecto, adivina otra vez: "
  num_usuario = gets.chomp.to_i
end
puts "Adivinaste, felicidades"

# Utilizando do-while
begin
  print "Adivina el número mágico: "
  num_usuario = gets.chomp.to_i
end while num_usuario != num_magico
# Esta sentencia se ejecuta al menos una vez ya que evalúa la condición al final
puts "Adivinaste, felicidades"
```

Otros menos utilizados:

``` rb
# times
10.times do |i|
  puts i
end
# 0, 1, 2, 3, 4, 5, 6, 7, 8, 9

# upto
1.upto(10) do |i|
  puts i
end
# 1, 2, 3, 4, 5, 6, 7, 8, 9, 10

# downto
10.downto(1) do |i|
  puts i
end
# 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

### 7.5. Matrices

Una matriz corresponde a un arreglo de **dos dimensiones** cuya principal característica radica en que sus arreglos internos deben tener la misma cantidad de elementos.

``` rb
require 'matrix'

arreglo = [[1,2,3],[1,2,3]]  # Matriz
arreglo_dos = [[1,2,3],[1,2]]  # Arreglo de dos dimensiones
matriz = Matrix[[1,2,3],[1,2,3]]  # Matriz inicializada de otra forma
```

Adicionalmente, todos sus elementos deben ser de tipo numérico.

Al igual que con los arreglos unidimensionales, tenemos una gran variedad de métodos para las matrices. Algunos de ellos son:

``` rb
# Recorrer una matriz (primero abarca la fila y luego la columna)
matriz = [[1,2,3],[4,5,6]]
matriz.each do |i|
  puts i
end
# 1 2 3
# 4 5 6

matriz_dos = [[1,2,3],[4,5,6],[7,8,9]]  # Matriz cuadrada
# 1 2 3
# 4 5 6
# 7 8 9

# Diagonal de una matriz
matriz_dos.each(:diagonal) do |i|
  puts i
end
# 1 5 9

# Elementos que se encuentran por debajo de la diagonal de una matriz
matriz_dos.each(:strict_lower) do |i|
  puts i
end
# 4 7 8

# Elementos que se encuentran por encima de la diagonal de una matriz
matriz_dos.each(:strict_upper) do |i|
  puts i
end
# 2 3 6
```

## 8. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°3](https://nisoto.github.io/rails-iii-instalacion/){: .btn .btn-info} | [Lección N°5 >](https://nisoto.github.io/rails-v-ruby-avanzado/){: .btn .btn-info} |
