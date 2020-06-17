---
layout: post
title: "Bases de Datos III: Base de datos y Tablas"
date: 2020-06-02
excerpt: "Capítulo N°3 del curso de Bases de Datos"
tags: [mysql]
---

## 1. Variables

No olvidemos que una **variable** corresponde a un espacio reservado en la memoria que, como su nombre lo indica, puede cambiar su contenido a lo largo de la ejecución de un programa. En MySQL podemos declarar una variable de la siguiente manera:

``` sql
SET @variable = valor;
```

También podemos declarar varias variables en una misma línea:

``` sql
SET @var1 = valor1, @var2 = valor2, @var3 = valor3;
```

Para imprimir el valor de nuestras variables, utilizamos el comando **SELECT** (DML):

``` sql
SELECT @variable;
```

Algunos ejemplos:

``` sql
SET @nombre = "Nicolas";
SET @curso = "Base de datos", @gestor = "Mysql";
SELECT @nombre, @curso, @gestor;
```

**Importante**: Las variables que creemos en nuestra sesión de MySQL solo pertenecerán a dicha sesión (ya sea para consultarlas, modificarlas y/o eliminarlas). Si cerramos la sesión y abrimos una nueva, nuestrar variables se habrán perdido.

## 2. Crear una Base de Datos

Para **crear** una nueva Base de Datos en cualquier SGBD utilizamos el comando **CREATE** (DDL):

``` sql
CREATE DATABASE nombrebdd;
```

Las Bases de Datos que vayamos creando en MySQL podremos visualizarlas mediante la palabra reservada **SHOW**:

``` sql
SHOW DATABASES;
```

Por último, si quisiéramos eliminar una Base de Datos, utilizamos el comando **DROP** (DDL):

``` sql
DROP DATABASE nombrebd;
```

**Importante**: Este comando borrará de manera definitiva la base de datos, lo que significa que **no podremos** recuperarla.

Algo que debemos tener en cuenta a la hora de trabajar sobre algún SGBD es **especificar** la Base de Datos, para ello utilizamos la palabra reservada **USE**:

``` sql
USE nombrebdd;
```

## 3. Crear una Tabla

Una vez hayamos creado nuestra Base de Datos, el siguiente paso sería crear las **Tablas** que formarán parte de este universo. Para ello conviene seguir ciertos pasos para así asegurar una optimización de recursos y no caer en la redundancia de cierta información:

1. Definir los campos que la compondrán.
2. Realizar una **Normalización**.
3. Crear la tabla en la Base de Datos.

Pongamos como ejemplo el caso de una **librería**, en donde tenemos muchos **libros** escritos por diferentes **autores**. Si llevamos esto a MySQL, tendremos algo como lo siguiente:

#### 1. Definir los campos que la compondrán

Este proceso consiste en definir los posibles campos que contendrá la tabla que vamos a crear. Para este ejemplo consideraremos a un **Autor**, el cual obviamente tiene un nombre, sexo, fecha de nacimiento y país de origen, entre otros.

* **Nombre**: Una cadena de caracteres.
* **Género**: Solo un caracter, el cual puede ser **M** (Masculino) o **F** (Femenino).
* **Fecha de nacimiento**: Una fecha (día, mes y año).
* **País de origen**: Una cadena de caracteres al igual que Nombre.

#### 2. Realizar una Normalización

Este proceso consiste en desglosar los campos definidos en la etapa anterior para así no caer en la redundancia y optimizar al máximo los recursos. 

* **Id del autor**: Un número entero y único (una especie de código).
* **Nombre**: Una cadena de caracteres.
* **Apellido**: Separamos el apellido del nombre del autor.
* **Género**: Solo un caracter, el cual puede ser **M** (Masculino) o **F** (Femenino).
* **Fecha de nacimiento**: Una fecha (día, mes y año).
* **País de origen**: Una cadena de caracteres al igual que Nombre.

#### 3. Crear la tabla en la Base de Datos

Una vez hayamos normalizado nuestra tabla, podemos crearla en la Base de Datos utilizando el comando **CREATE**:

CREATE TABLE autores(
autor_id INT,
nombre VARCHAR(30),
apellido VARCHAR(30),
genero CHAR(1),
fecha_nacimiento DATE,
pais_origen VARCHAR(40)
);

**Nota**: El siguiente apartado detalla los tipos de datos existentes en cualquier SGBD y sus limitaciones.
