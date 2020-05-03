---
layout: post
title: "Ruby on Rails IX: Modelos"
date: 2020-04-30
excerpt: "Capítulo N°9 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ActiveRecord

**ActiveRecord** corresponde a una capa que nos permite acceder y manipular la información de la base de datos sin la necesidad de escribir SQL, ya que sigue rigurosamente el estándar **ORM** (Object-Relational Mapping o Mapeo Objeto-Relacional en español), es decir, **Tablas en Clases**, **Registros en Objetos** y **Campos en Atributos**.

El concepto más importante de ActiveRecord es el **modelo**. Un modelo es una clase de Ruby que, de acuerdo al estándar ORM, representa una tabla en la base de datos:

``` rb
class Article < ApplicationRecord
end
```

No olvidemos que los modelos se encuentran en la carpeta `app/models`.

En Ruby on Rails por convención, el nombre de la tabla en la base de datos es el mismo nombre del modelo pero sin capitalizar y en plural (`articles` en este caso).

Algo importante a considerar es que en el modelo no se definen las columnas de la tabla explícitamente, ya que ActiveRecord las toma de la tabla directamente.

## 2. Primer modelo

A lo largo de este curso construiremos un Blog Personal, por lo que partiremos creando nuestro primer modelo o tabla: los **artículos** de nuestro blog. Aunque es posible crear la tabla y el modelo manualmente, es más sencillo utilizar el generador de modelos que incluye Rails:

```
$ rails generate model Article title:string description:text
```

Varias cosas a tener en cuenta:
* Tal como lo vimos en el capítulo anterior cuando creamos el controlador `dashboard`, podemos utilizar tanto `rails generate` como `rails g`.
* Lo recomendable es que el nombre del modelo esté capitalizado y en singular (así, la tabla en la base de datos para este caso llevará por nombre `articles`).
* Los campos del modelo deben ir separados por un espacio.
* El tipo de dato de los campos se define luego de los dos puntos (sin espacios).
* Los tipos de dato generalmente utilizados son : `string`, `text`, `integer`, `decimal`, `date`, `time`, `datetime`, `boolean` y `references`.
* Podemos definir la longitud máxima de un `string` utilizando llaves (`string{10}` por ejemplo).
* Si omitimos el tipo de dato, Rails por defecto asume que es `string{255}`.
* Al igual que otros Frameworks que trabajan con **ORM**, al momento de crear el modelo se generarán automáticamente 3 campos adicionales: `id` (llave primaria, de tipo entero y autoincrementable), `created_at` y `updated_at` (con estos dos últimos campos podemos saber cuando se creó un registro y cuando se modificó por última vez, respectivamente).

El comando anterior creará varios archivos, entre los cuales tenemos:
* El modelo (clase Article), ubicado en `app/models/article.rb`.
* Un archivo en `db/migrate` con las instrucciones para crear la tabla en la base de datos, conocido como **migración**.

Para crear la tabla debemos ejecutar:

```
$ rails db:migrate
```

Y tendremos nuestro primer modelo creado con éxito.

## 3. Utilizando nuestro modelo

Lo normal es que teniendo un modelo queramos listar, crear, modificar y/o eliminar registros de la tabla que representa, a lo cual se le conoce como **CRUD** (Create, Read, Update, Delete). Por el momento trabajaremos sobre nuestro modelo `Article` desde la consola de Rails, pero ten en cuenta que esto se realiza desde los **controladores**.

Para abrir la consola, debemos ejecutar el siguiente comando en la terminal:

```
$ rails console
```

La consola de Rails es un ambiente similar a **IRB**, con la diferencia de que en este medio accedemos a las clases de nuestra aplicación.

### 3.1. Creando un registro

Para crear un nuevo registro en la base de datos, debemos instanciar el modelo Article y utilizar el método `save`:

``` rb
article1 = Article.new(title: "Mi primer articulo", description: "Este es mi primer articulo")
article1.save
```

Aunque existe una forma equivalente pero un poco más corta:

``` rb
article1 = Article.create(title: "Mi primer articulo", description: "Este es mi primer articulo")
```

### 3.2. Encontrando registros específicos

Cuando creamos un registro, la base de datos automáticamente le asigna un `id` único que podemos utilizar para encontrar dicho registro, a través del método `find`:

``` rb
article = Article.find(1)
article.title  # "Mi primer articulo"
article.description  # "Este es mi primer articulo"
```

### 3.3. Actualizando registros

Para actualizar la información de un registro podemos utilizar el método `save` nuevamente:

``` rb
article = Article.find(1)
article.title = "Modificando el primer articulo"
article.save
```

Aunque es más común utilizar el método `update`:

``` rb
article = Article.find(1)
article.update(title: "Modificando el primer articulo")
```

También es posible actualizar varios registros a la vez utilizando `update_all`:

``` rb
article.update_all(title: "Primer articulo")
# Actualizamos el nombre de todos los articulos a "Primer articulo"
```

### 3.4. Eliminando registros

Para eliminar un registro, utilizamos el método `destroy`:

``` rb
article = Article.find(1)
article.destroy
```

### 3.5. Listando registros

Existen muchas formas de listar nuestros registros, los más utilizados son:

``` rb
# Retorna una colección con todos los articulos
article = Article.all

# Retorna el primer articulo
article = Article.first

# Retorna el último articulo
article = Article.last

# Retorna el libro con id 1
article = Article.find(1)

# Retorna el primer articulo con nombre "Primer articulo"
article = Article.find_by(title: "Primer articulo")
```

Otra forma de buscar un registro es utilizando el método `where`:

``` rb
article = Article.where(title: "Primer articulo").take
```

Este método por lo general se usa para consultas complejas y retorna una colección de registros (por eso agregamos `take` en el ejemplo anterior, que obtiene el primer elemento de la colección).

`where` también puede recibir una cadena para crear consultas más complejas. Veamos otro ejemplo:

``` rb
expensive_books = Book.where("price > 20")
```

Por temas de rendimiendo y seguridad (especialmente cuando las condiciones vienen de los usuarios), se recomienda cambiar el ejemplo anterior por lo siguiente:

``` rb
expensive_books = Book.where("price > ?", 20)
```

Los signos de interrogación se van a reemplazar por los siguientes argumentos del `where`, en el orden en el que aparecen.

### 3.6. Ordenando registros

Podemos utilizar el método `order` para ordenar los registros. Por ejemplo, ordenaremos los artículos de acuerdo a su `id`:

``` rb
articles = Article.all.order(:id)
```

Y de forma descendente sería:

``` rb
articles = Article.all.order(id: :desc)
```

### 3.7. Limitar el número de registros

Podemos utilizar el método `limit` y `offset` para limitar el número de registros y/o saltar algunos respectivamente.

Por ejemplo, traer un máximo de 5 artículos:

``` rb
articles = Article.limit(5)
```

O también traer 5 artículos, saltándonos los primeros 30:

``` rb
articles = Article.limit(5).offset(30)
```

### 3.8. Iterando sobre los registros

Con el método `each` podemos recorrer nuestra colección de artículos:

``` rb
articles = Article.all
articles.each do |article|
  puts article.title
end
```

## 4. ¡No olvidar!

No olvidemos todo lo aprendido en las lecciones de Ruby básico y avanzado, ya que Rails fue creado para trabajar con este lenguaje de programación.

### 4.1. Métodos que invocamos sobre la clase

A continuación tenemos algunos de los métodos más comunes que invocamos directamente sobre la clase:

``` rb
Article.all  # Retorna una colección
Article.first  # Retorna un único registro
Article.last  # Retorna un único registro
Article.find(3)  # Retorna un único registro
Article.find_by(title: "Primer articulo")  # Retorna un único registro
Article.where(title: "Primer articulo")  # Retorna una colección
```

Algunos retornan un único registro, mientras que otros una colección de registros.

### 4.2. Métodos que invocamos sobre un registro

Los métodos que generalmente vamos a invocar sobre una instancia (que representa un registro) son:

``` rb
article.title
article.title = "Segundo articulo"
article.save
article.update(title: "Tercer articulo")
article.destroy
```

|     |     |
|:----|----:|
| [< Lección N°8](https://nisoto.github.io/rails-viii-ruby-on-rails/){: .btn .btn-info} | [Inicio >](https://nisoto.github.io/blog/){: .btn .btn-info} |
