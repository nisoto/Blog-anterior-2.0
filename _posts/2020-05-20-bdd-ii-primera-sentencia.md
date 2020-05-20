---
layout: post
title: "Bases de Datos II: Primera sentencia"
date: 2020-05-20
excerpt: "Capítulo N°2 del curso de Bases de Datos"
tags: [mysql]
---

## 1. Grupos de comandos SQL

Tal como lo vimos en el capítulo anterior, los comandos en SQL se dividen en 4 grupos:

### 1.1. Data Definition Language (DDL)

**Lenguaje de Definición de Datos** en español, se utilizan para crear y modificar la estructura de una base de datos.

* CREATE
* ALTER
* DROP
* TRUNCATE

### 1.2. Data Manipulation Language (DML) 

**Lenguaje de Manipulación de Datos** en español, se utilizan para seleccionar, insertar, actualizar y borrar de manera definitiva, registros en una base de datos (consultas de selección y acción).

* SELECT
* INSERT
* UPDATE
* DELETE

### 1.3. Data Control Language (DCL)

**Lenguaje de Control de Datos** en español, proporcionan seguridad a la información de una base de datos.

* GRANT
* REVOKE

### 1.4. Transaction Control languaje (TCL)

**Lenguaje de Control de Transacciones** en español, se preocupan de la gestión de cambios en los datos.

* COMMIT
* ROLLBACK
* SAVEPOINT

## 2. Cláusulas

Las cláusulas en SQL corresponden a las condiciones que modificarán nuestras consultas y son utilizadas para definir los datos que deseamos manipular.

1. FROM: Especifica la **tabla** de la que se quieren obtener los registros.
2. WHERE: Especifica las condiciones o criterios de los registros seleccionados.
3. GROUP BY: Nos permite agrupar los registros seleccionados en función de un campo.
4. HAVING: Especifica las condiciones o criterios que deben cumplir los grupos (GROUP BY).
5. ORDER BY: Ordena los registros seleccionados en función de un campo.

Debemos tener en cuenta que las cláusulas tienen cierto **orden de escritura** (FROM, WHERE, GROUP BY, HAVING y ORDER BY respectivamente).

## 3. Instrucción SQL

A partir de los apartados anteriores, una instrucción SQL corresponderá a la unión entre **comandos**, **cláusulas**, **operadores** y **funciones de agregado**, es decir:

**Instrucción SQL** = **Comando** + **Cláusula** + **Operadores** + **Funciones de agregado**

Hay que tener en cuenta que una instrucción SQL no necesariamente debe contar con estos 4 componentes (eso dependerá de su complejidad). Los componentes **Comando** y **Cláusula** son obligatorios.

## 4. Primera sentencia SQL

Para construir nuestra primera sentencia, vamos a considerar la siguiente tabla que almacena los datos de ciertos autores de novelas:

| Autor_id | Nombre  | Apellido | Seudonimo       | Genero | Fecha_nacimiento | Pais_origen |
|:--------:|:-------:|:--------:|:---------------:|:------:|:----------------:|:-----------:|
| 1        | Stephen | King     | Richard Bachman | M      | 27-09-1947       | USA         |
| 2        | Joanne  | Rowling  | J. K. Rowling   | F      | 25-09-1947       | Reino Unido |

Supongamos que queremos listar solamente el nombre y apellido del autor Stephen King. Para ello, debemos hacernos como mínimo estas 3 preguntas:

1. ¿Qué datos nos están pidiendo? El **nombre** y **apellido**.
2. ¿Dónde están esos datos? En la tabla **autores**.
3. ¿Qué requisitos deben cumplir los registros? Que sean solamente los datos de **Stephen King**.

A partir de nuestras respuestas podemos construir nuestra consulta mediante pseudocódigo:

Seleccioname el Nombre y Apellido
De la tabla Autores
Cuyo Nombre sea Stephen y su Apellido sea King

También podemos ayudarnos del identificador único (Autor_id) para este autor:

Seleccioname el Nombre y Apellido
De la tabla Autores
Cuyo Autor_id sea igual a 1

Si llevamos esta sentencia a SQL, tendríamos algo como lo siguiente:

``` sql
SELECT nombre, apellido  -- Comando SELECT
FROM autores             -- Cláusula FROM
WHERE Autor_id = 1       -- Cláusula WHERE
```

¡Hemos construido nuestra primera sentencia! Y como te habrás dado cuenta, posee 3 de los 4 componentes que conforman una instrucción SQL: el comando **SELECT**, las cláusulas **FROM** y **WHERE**, y el operador de igualdad (`=`)

|     |     |
|:----|----:|
| [< Lección N°1](https://nisoto.github.io/bdd-i-introduccion/){: .btn .btn-info} | [Inicio >](https://nisoto.github.io/curso-bases-de-datos/){: .btn .btn-info} |
