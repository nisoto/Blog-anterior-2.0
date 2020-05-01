---
layout: post
title: "Ruby on Rails IX: Arquitectura"
date: 2020-04-30
excerpt: "Capítulo N°9 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Componentes de Rails

Los componentes más importantes de Ruby on Rails son:

1. **El enrutador**, que se configura en el archivo `config/routes.rb` y nos permite asociar las rutas con las acciones.
2. **Los controladores**, que se encuentran en la carpeta `app/controllers` y almacenan las acciones.
3. **Las vistas**, que se encuentran en `app/views` y nos permiten definir el código HTML que se renderiza desde los controladores.
4. **ActiveRecord**, el cual nos va a permitir interactuar con la base de datos.
5. La aplicación de **consola**, que nos permitirá ahorrar tiempo de desarrollo.

### 1.1. El enrutador

El enrutador es el componente que decide qué controlador y qué modelo va a procesar una petición HTTP, y se configura en el archivo `config/routes.rb`. Existen varias formas de definir las rutas, veamos la más genérica:

``` rb
get '/index', to: 'dashboard#index'
```

En este ejemplo estamos diciendo que cuando alguien haga una petición a `GET /index`, el método `index` del controlador `DashboardController` (ubicado en `app/controllers/dashboard_controller.rb`) es el que se va a encargar de procesar la petición.

Otra forma equivalente es utilizar el operador `=>`, es decir:

``` rb
get '/index' => 'dashboard#index'
```

Por último, es posible omitir el controlador y el método, siempre y cuando la ruta tenga la forma `/controlador/método`. Por ejemplo, la siguiente línea utilizará el método `index` del controlador `DashboardController`

``` rb
get '/dashboard/index'
```

### 1.2. Los controladores

Los controladores son **clases** de Ruby con métodos que se van a encargar de procesar las peticiones HTTP.

``` rb
class DashboardController < ApplicationController
  def index
  end
end
```

### 1.3. Las vistas

Podemos utilizar vistas para no tener que escribir todo el código HTML en las acciones (que es posible pero muy engorroso). Por convención, Rails renderiza una vista por defecto que se encuentra en una ubicación específica y se llama de una forma específica:

* El nombre del archivo debe ser igual al método seguido de `.html.erb`.
* Se debe ubicar en la carpeta `app/views`, dentro de una carpeta que tenga el mismo nombre del controlador.

Por ejemplo, el método `index` del controlador `dashboard` va a renderizar la vista `app/views/dashboard/index.html.erb`

``` rb
class DashboardController < ApplicationController
  def index
  end
end
```

#### 1.3.1. Pasando información del controlador a la vista

Cuando definimos una variable de instancia en la acción, esta variable va a estar disponible en la vista. Por ejemplo

``` rb
class DashboardController < ApplicationController
  def index
    @name = "Nicolas"
  end
end
```

La variable `@name` va a estar disponible en la vista `app/views/dashboard/index.html.erb` y la podríamos imprimir de la siguiente forma:

``` erb
<h1>Hola <%= @name %></h1>
```

La etiqueta `<%= contenido %>` le indica a Rails que queremos imprimir la variable en pantalla. Si solo quisiéramos evaluar código (pero no imprimir) ignoramos el `=`, es decir, `<% contenido %>`. Por ejemplo:

``` erb
<% [1,2,3,4].each do |number| %>  <!-- Evalúa -->
  <p>Numero: <%= number %></p>  <!-- Imprime -->
<% end %>
<!--
Numero: 1
Numero: 2
Numero: 3
Numero: 4
-->
```

#### 1.3.2. Query String

El **query string** corresponde al conjunto de propiedades que van después del signo de interrogación (?) de un URL. Rails automáticamente convierte las propiedades en un `hash params` al que podemos acceder desde el controlador o la vista.

Por ejemplo, si queremos obtener el valor de una propiedad llamada `name` utilizaríamos `params[:name]`. Modifiquemos `app/views/dashboard/index.html.erb` para que quede de la siguiente manera:

``` erb
<h1>Hola <%= params[:name] %></h1>
```

Si ingresamos a [http://localhost:3000/?name=Nicolas](http://localhost:3000/?name=Nicolas), deberíamos ver en pantalla **"Hola Nicolas"**. Puedes probar cambiando el query string con otros nombres.

Debes tener en cuenta que los valores del query string siempre llegan como cadenas de texto, por lo que si deseas otro tipo de dato, se debe convertir manualmente. Por ejemplo:

``` erb
<h1>En cinco años tendrás <%= params[:age].to_i + 5 %> años</h1>
```

En este caso, estamos convirtiendo la propiedad `age` a un entero para poder sumarle `5`.

### 1.4. ActiveRecord

**ActiveRecord** es una clase cuyo propósito es la administración y funcionamiento de los modelos, proporcionándonos la capa **objeto-relacional** que sigue rigurosamente el estándar **ORM**, es decir, **Tablas en Clases, Registros en Objetos y Campos en Atributos**. Esto facilita el entendimiento del código asociado a la base de datos y encapsula la lógica específica, haciendo más fácil su uso para los programadores.

Sus principales ventajas son:
* Manejo de entidades como objetos.
* Las acciones del CRUD están encapsuladas así que se reduce el código y se hace más fácil de comprender.
* El código es fácil de entender y mantener.
* Se reduce considerablemente el uso de SQL, lo que implica cierta independencia con el manejador de base de datos que utilizamos.

### 1.5. La aplicación de consola

Una de las razones por las que Ruby on Rails es tan popular se debe a que incorpora una poderosa aplicación de consola que nos permite, entre otras cosas, generar código a través de comandos llamados **generadores**

Hasta el momento hemos visto los siguientes comandos:

* `rails new`, que nos permite crear una nueva aplicación.
* `rails server`, que nos permite iniciar el servidor.
* `rails generate controller`, que nos permite crear un controlador.

Iremos descubriendo nuevos comandos a medida que avancemos en este curso.

## 2. Trabajando en nuestro Blog Personal

A lo largo de este curso construiremos un Blog Personal, por lo que partiremos creando un nuevo controlador de nombre `articles`, el cual contendrá todas las acciones que posee un CRUD básico: listar, crear, editar y eliminar.

Para crear este controlador vamos a la terminal y ejecutamos:

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

Hola amigos.

|     |     |
|:----|----:|
| [< Lección N°8](https://nisoto.github.io/rails-viii-ruby-on-rails/){: .btn .btn-info} | [Inicio >](https://nisoto.github.io/blog/){: .btn .btn-info} |
