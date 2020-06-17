---
layout: post
title: "Bases de Datos III: Base de datos y Tablas"
date: 2020-05-20
excerpt: "Capítulo N°3 del curso de Bases de Datos"
tags: [mysql]
---

# 1. Variables

No olvidemos que una **variable** corresponde a un espacio reservado en la memoria que, como su nombre lo indica, puede cambiar su contenido a lo largo de la ejecución de un programa. En MySQL podemos declarar una variable de la siguiente manera:

``` sql
SET @variable = valor;
```

También podemos declarar varias variables en una misma línea:

``` sql
SET @var1 = valor1, @var2 = valor2, @var3 = valor3;
```

Para imprimir el valor de nuestras variables, utilizamos el comando **SELECT**:

``` sql
select @variable;
```

**Nota**: Más adelante veremos en detalle el comando `SELECT`.

Ejemplos:

SET @nombre = "Nicolas";

+---------+
| @nombre |
+---------+
| Nicolas |
+---------+

SET @nombre = "Nicolas", @curso = "Base de datos", @gestor = "Mysql";

select @nombre, @curso, @gestor;

+---------+---------------+---------+
| @nombre | @curso        | @gestor |
+---------+---------------+---------+
| Nicolas | Bade de datos | Mysql   |
+---------+---------------+---------+

IMPORTANTE!! -> las variables que creamos en la sesión, solo le pertenecen a la sesión!! (consultarlas, modificarlas o eliminarlas)

Si cerramos sesión, nuestras variables se han perdido!
