---
layout: post
title: "Bases de Datos I: Introducción"
date: 2020-05-19
excerpt: "Capítulo N°1 del curso de Bases de Datos"
tags: [mysql]
---

## 1. ¿Qué se aprenderá?

* Todo sobre **SQL** (Lenguaje de Consultas Estructurado). Es decir, tablas, vistas, subconsultas, procedimientos, transacciones y triggers, entre otros.
* El **Sistema de Gestión de Bases de Datos** MySQL.

## 2. Base de Datos

### 2.1. ¿Qué es?

una **Base de Datos** corresponde a una serie de datos organizados y relacionados entre si, los cuales son recolectados y explotados (o trabajados) por los distintos sistemas de información de una empresa o negocio en particular.

Si traducimos al español la definición anterior, tenemos que una Base de Datos es una especie de **Almacén** de datos, en el cual guardaremos productos (información o registros), y estos serán recolectados y trabajados por una empresa o negocio.

### 2.2. Sistema de Gestión de Bases de Datos

Comúnmente abreviado **SGBD**, corresponde a un tipo de **software** muy específico, dedicado a servir  de interfaz entre la base de datos, el usuario y las aplicaciones que la utilizan.

Un SGBD se compone de un **Lenguaje de Definición de Datos**, un **Lenguaje de Manipulación de Datos** y un **Lenguaje de Consulta**.

Entre los tantos SGBD que existen destacan **MySQL** (con el cual trabajaremos a lo largo del curso), **Oracle** y **Microsoft SQL Server**, entre otros.

### 2.3. Estructura mínima de almacenamiento

* **Tabla**: Objeto de almacenamiento perteneciente a una Base de Datos (BDD) el cual corresponde a una estructura donde se almacenan registros o filas de datos. Cada tabla posee un nombre único en la BDD.
* **Registro**: Corresponde a cada una de las filas de una tabla. Está compuesto por cambos o atributos.
* **Campo**: Corresponde a cada uno de los *cajoncitos* de un registro donde se guardan los datos. Cada campo posee un nombre único para la tabla de la cual forma parte y además, es de un tipo (naturaleza) determinado.

![TablaBDD]({{ site.baseurl }}/assets/img/TablaBDD.jpg)

## 3. SQL

### 3.1. ¿Qué es?

**Lenguaje Estructurado de Consultas** (**Structured Query Language** por sus siglas en inglés), corresponde a un lenguaje de programación diseñado para almacenar, manipular y recuperar datos en una base de datos relacional

La primera versión de SQL surgió en 1974, cuando un grupo de **IBM** desarrolló el primer prototipo de una base de datos relacional. Años más tarde, **Relational Software** (que luego se convertiría en **Oracle**) lanzó la primera base de datos relacional comercial.

Funcionamiento de SQL:

![FuncionamientoSQL]({{ site.baseurl }}/assets/img/FuncionamientoSQL.jpg)

Importante:
* SQL **no es considerado** un lenguaje de programación propiamente tal debido a que carece de las estructuras que posee un lenguaje de programación típico (como condicionales y bucles, por ejemplo), por lo que es comúnmente llamado **lenguaje de accceso a datos**.

### 3.2. Estándar SQL

SQL comenzó a convertirse en un lenguaje por excelencia en los diversos SGBD, logrando así que en 1986 sea estandarizado por **ANSI**, dando lugar a la primera versión estándar de este lenguaje: **SQL-86** o **SQL-1**. Al año siguiente, este estándar también es adoptado por **ISO**.

ANSI SQL a sufrido varias revisiones y agregados a lo largo del tiempo, siendo **SQL:2016** su última versión.

### 3.3. Grupos de comandos SQL

Los comandos que podemos utilizar en SQL se dividen en 4 grandes grupos:

1. **DDL**: Cuyas siglas significan **Data Definition Language** (Lenguaje de Definición de Datos), se utilizan para crear y modificar la estructura de una base de datos.
2. **DML**: Cuyas siglas significan **Data Manipulation Language** (Lenguaje de Manipulación de Datos), se utilizan para seleccionar, insertar, actualizar y borrar de manera definitiva, registros en una base de datos (consultas de selección y acción).
3. **DCL**: Cuyas siglas significan **Data Control Language** (Lenguaje de Control de Datos), proporcionan seguridad a la información de una base de datos.
4. **TCL**: Cuyas siglas significan **Transaction Control languaje** (Lenguaje de Control de Transacciones), se preocupan de la gestión de cambios en los datos.

## 4. MySQL

Tal como lo mencionamos en un principio, **MySQL** es un **Sistema de Gestión de Bases de Datos** (SGBD) relacional desarrollado bajo licencia dual: Licencia pública general y Licencia comercial por Oracle.

Es considerada como la base de datos de **código abierto** más popular del mundo (junto a Oracle y Microsoft SQL Server), sobre todo en entornos de desarrollo web.

MySQL fue inicialmente desarrollada por **MySQL AB**, la cual fue adquirida por **Sun Microsystems** en 2008 y luego comprada por **Oracle Corporation** en 2010. Esta última ya era dueña desde el 2005 de **Innobase Oy**, una empresa finlandesa desarrolladora del motor InnoDB para MySQL.

Este gestor es usado por muchos sitios web grandes y populares, como **Wikipedia**, **Google**, **Facebook**, **Twitter** y **YouTube**, entre otros.

Cabe destacar que está desarrollado en su mayor parte con los lenguajes de programación C y C++.

|     |     |
|:----|----:|
| [< Inicio](https://nisoto.github.io/curso-bases-de-datos/){: .btn .btn-info} | [Lección N°2 >](https://nisoto.github.io/bdd-ii-primera-sentencia/){: .btn .btn-info} |
