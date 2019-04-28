---
layout: post
title: "Curso de Ruby III: Variables"
date: 2019-04-28
excerpt: "Capítulo N°3 del curso de Ruby"
tags: [ruby]
---

# Variables

Una variable corresponde a un espacio de memoria que, como su nombre lo indica, puede cambiar su contenido a lo largo de la ejecución de un programa. Supongamos que tenemos la siguiente línea de código:

``` ruby
name = "Nicolas"
```

En el ejemplo anterior, `name` es el **nombre** de la variable, `=` corresponde al **operador de asignación**, el cual le indica a la variable que debe guardar lo que se encuentra a la derecha de este operador (en este caso, una cadena de texto) y "Nicolás" es el valor que guarda la variable.

A diferencia de otros lenguajes como Java, en Ruby no es necesario especificar el tipo de dato de una variable ya que el intérprete deduce cual es el tipo a partir del valor.

¿Y si ahora queremos mostrar en pantalla el valor almacenado en la variable `name`? En el capìtulo anterior escribimos el clásico "Hola Mundo" utilizando el comando `puts`, el cual nos sirve para desplegar por pantalla un valor como una cadena, un número y/o un objeto.

``` ruby
name = "Nicolas"
puts name
```

Si quisieramos cambiar el valor de la variable `name` a 25, esto sería totalmente válido (cosa que en varios lenguajes resultaría en un error) ya que como se dijo anteriormente, Ruby deduce el tipo de dato. Por ejemplo:

``` ruby
name = "Nicolas"
puts name
name = 25
puts name
```

El programa mostraría por pantalla la cadena "Nicolas" y luego el número 25.

**Nota:** en resumidas cuentas, una variable es un **identificador de un dato**.

## Inicialización de variables

A la hora de trabajar con variables, puede darse el caso que contengan más de una palabra. Por lo general, se suele separar cada palabra con un guión bajo, por ejemplo:

``` ruby
nombre_del_tutor = "Nicolas"
```

Esta práctica se conoce como **Snake case** (Víbora) y recibe este nombre ya que todo se encuentra en un mismo nivel y separado por guiones.

Existe otra práctica que hace uso de las mayúsculas (ignorando el guión bajo) y se conoce como **Camel case**. Si tomamos el ejemplo anterior sería algo como:

``` ruby
nombreDelTutor = "Nicolas"
```

El tipo de práctica a utilizar dependerá netamente del programador, aunque por temas de legibilidad conviene utilizar **Snake case**. Lo importante es que los nombres de las variables sean muy expresivas.

Existen algunas restricciones que deberías considerar a la hora de trabajar con variables:

1. A una variable no debes darle nombres de palabras reservadas del lenguaje (tales como `new`, `def`, `if`, etc.). Si eres un principiante en el mundo de la programación, las palabras reservadas por lo general toman un color azul.
2. No debes colocar la primera letra del nombre de una variable con mayúsculas porque en ese caso estarías hablando de una **constante**.
3. El nombre de una variable no puede comenzar con un número ya que esto generaría un error.

## Constantes

Una constante se diferencia a una variable en que **no cambia durante la ejecución de un programa**. En el apartado anterior se hizo una mención a ellas, en donde se especificó que la primera letra del nombre debe estar en mayúsculas, por ejemplo:

``` ruby
Pi = 3.14
Nombre_del_tutor = "Nicolas"
```

Cabe destacar que utilizar sólo mayúsculas igual funciona, es decir:

``` ruby
NUM = 1
NOMBRE = "Nicolas"
```

También son constantes válidas en Ruby.

# Números

Dentro de lo que son los números tenemos dos importantes tipos o grupos: 

* **Enteros** (`int`): No tienen punto decimal.
* **Punto Flotante** (`float`): Contienen al menos un dígito después del punto.

Algunos ejemplos:

``` ruby
x = 20      # Entero
y = 20.0    # Punto flotante
z = 365     # Entero
w = 3.1415  # Punto flotante
```

## Ejecutando operaciones aritméticas

Lo primero que vas a querer hacer con los números será ejecutar cálculos matemáticos. Para ello, solo basta con colocar el respectivo operador y listo, es decir:

``` ruby
x = 20
y = 2
puts x + y  # 22
puts x - y  # 18
puts x * y  # 40
puts x / y  # 10
```

Más adelante veremos con detalle estos operadores, donde prima la preferencia que ocupa cada uno.

## Diferencia entre trabajar con Enteros y Punto Flotante

Supongamos que queremos ejecutar la siguiente operación:

``` ruby
x = 10
y = 3
puts x / y  # 3
```

Aunque no lo creas, el resultado es `3`. Esto se debe a que al tratarse de dos números Enteros, se ejecuta una divisón normal entre dos Enteros, donde el resultado es `3` y el resto `1` (valor que no se está mostrando).

Para solucionar este inconveniente, debemos tratar ambos números como Punto Flotante:

``` ruby
x = 10.0
y = 3.0
puts x / y  # 3.3333333333333335
```

Esta vez tenemos el resultado esperado.

## Casting o Conversión de Números

En el primer capítulo se mencionó que en Ruby **todo es un objeto**, esto significa que los números son un objeto, y todo objeto tiene sus respectivos métodos:

``` ruby
x = 10
puts x.to_f  # 10.0
```

El método `to_f` **convierte un número Entero en Punto Flotante**.

``` ruby
y = 12.23
puts y.to_i  # 12
```

El método `to_i` **convierte un número de Punto Flotante en Entero**. Aquí es importante destacar que al momento de realizar la conversión, se toma la parte entera realizando un truncamiento y **no** un redondeo (o aproximación).

Ya que los números son un objeto, lo siguiente son algunos de los métodos más conocidos:

``` ruby
# Determina el valor absoluto de un número
a = -10
puts a.abs  # 10

# Determina si un número es par o impar
b = 3
puts b.even?  # FALSE
# Imprimirá por pantalla TRUE si se trata de un par o FALSE en caso contrario

# Determina el sucesor de un número
c = 2
puts c.next  # 3
```

|     |     |
|:----|----:|
| [< Instalación](https://nisoto.github.io/curso-ruby-ii-instalacion/){: .btn .btn-info} | [Siguiente >](https://nisoto.github.io/blog/){: .btn .btn-info} |
