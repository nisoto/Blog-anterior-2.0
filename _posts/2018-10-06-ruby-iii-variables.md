---
layout: post
title: "Ruby III: Variables"
date: 2018-10-06
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

# Inicialización de variables

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

# Constantes

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