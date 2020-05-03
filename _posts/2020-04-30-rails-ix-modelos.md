---
layout: post
title: "Ruby on Rails IX: Modelos"
date: 2020-04-30
excerpt: "Capítulo N°9 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ¿Qué es?

**ActiveRecord** es una clase cuyo propósito es la administración y funcionamiento de los modelos, proporcionándonos la capa **objeto-relacional** que sigue rigurosamente el estándar **ORM**, es decir, **Tablas en Clases, Registros en Objetos y Campos en Atributos**. Esto facilita el entendimiento del código asociado a la base de datos y encapsula la lógica específica, haciendo más fácil su uso para los programadores.

Sus principales ventajas son:
* Manejo de entidades como objetos.
* Las acciones del CRUD están encapsuladas así que se reduce el código y se hace más fácil de comprender.
* El código es fácil de entender y mantener.
* Se reduce considerablemente el uso de SQL, lo que implica cierta independencia con el manejador de base de datos que utilizamos.

### 1.5. La aplicación de consola

Una de las razones por las que Ruby on Rails es tan popular se debe a que incorpora una poderosa aplicación de consola que nos permite, entre otras cosas, generar código a través de comandos llamados **generadores**.

Hasta el momento hemos visto los siguientes comandos:

* `rails new`, que nos permite crear una nueva aplicación.
* `rails server`, que nos permite iniciar el servidor.
* `rails generate controller`, que nos permite crear un controlador.

Iremos descubriendo nuevos comandos a medida que avancemos en este curso.

## 2. Trabajando en nuestro Blog Personal

A lo largo de este curso construiremos un Blog Personal, por lo que partiremos creando un nuevo controlador de nombre `articles`, el cual contendrá todas las acciones que posee un CRUD básico: listar, crear, editar y eliminar. Por el momento, solo nos centraremos en **listar** estos artículos.

Para crear el controlador, abrimos la terminal y ejecutamos:

```
$ rails generate controller articles
```

Ahora, nos dirigimos a `app/controllers/articles_controller.rb` para crear el método `index`:

``` rb
class ArticlesController < ApplicationController
  def index
    @articles = ["Article 1", "Article 2", "Article 3"]
  end
end
```

**Nota**: Aún no vamos a involucrar la base de datos, por lo que trabajaremos sobre un arreglo de Artículos con 3 elementos.

El siguiente paso es crear la vista de nombre `index.html.erb`, ubicada en `app/views/articles`:

``` erb
<h1>Listado de Artículos</h1>

<table>
  <thead>
    <tr>
      <th>Nombre</th>
    </tr>
  </thead>
  
  <tbody>
    <% @articles.each do |article| %>
      <tr>
        <td><%= article %></td>
      </tr>
    <% end %>
  </tbody>
</table>
```

Por último, debemos crear la ruta. Abrimos `config/routes.rb` y agregamos la siguiente línea de código:

``` rb
get '/articles', to: 'articles#index'
```

Si abrimos nuestro navegador e ingresamos a [http://localhost:3000/articles](http://localhost:3000/articles), podremos visualizar los 3 artículos que creamos en el método index.

|     |     |
|:----|----:|
| [< Lección N°8](https://nisoto.github.io/rails-viii-ruby-on-rails/){: .btn .btn-info} | [Inicio >](https://nisoto.github.io/blog/){: .btn .btn-info} |
