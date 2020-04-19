---
layout: post
title: "Ruby on Rails VIII: ¡Por fin Rails!"
date: 2020-04-16
excerpt: "Capítulo N°8 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Crear un proyecto

Para crear un nuevo proyecto en Rails (esto ya se vió en el capítulo anterior), debemos ejecutar el siguiente comando en la terminal:

```
rails new myapp
```

Con esto, Rails inmediatamente comenzará a crear varias carpetas y ficheros necesarios para nuestro proyecto y por último, instalará las **Gemas** (librerías) por defecto. Una vez terminado el proceso, para ingresar al directorio de nuestro proyecto ejecutamos:

```
cd myapp
```

Y luego podemos utilizar:

```
ls
```

Para visualizar todas las carpetas y ficheros que éste contiene.

## 2. Estructura de carpetas y ficheros

Si ejecutamos el comando `ls` dentro de la carpeta de nuestro proyecto podremos visualizar todas las carpetas y ficheros que éste contiene, los cuales poseen una estructura como la siguiente:

```
> .git
> app
> bin
> config
> db
> lib
> log
> node_modules
> public
> storage
> test
> tmp
> vendor
  .browserlistrc
  .gitignore
  .ruby-version
  babel.config.js
  config.ru
  Gemfile
  Gemfile.lock
  package.json
  postcss.config.js
  Rakefile
  README.md
  yarn.lock
```

No es necesario profundizar en todos y cada uno de los directorios y ficheros que se encuentran aquí, así que solo veremos los que estaremos utilizando a lo largo del desarrollo de nuestra aplicación:

* `app`: Dentro de este directorio tenemos varios subdirectorios, donde podemos destacar el **Modelo** (Models), la **Vista** (Views) y el **Controlador** (Controllers), es decir, el **Patrón MVC**.
* `config`: Este directorio contiene los principales ficheros que nos permiten configurar la aplicación, es decir, la configuración de la **Base de Datos** (`database.yml`), la estructura de su entorno (`environment.rb`) y las **Rutas** (`routes.rb`), entre otros.
* `db`: Dentro de este directorio se encuentra la **estructura de la Base de Datos**, es decir, todas las tablas existentes con sus respectivos atributos.
* `log`: Este directorio contiene los archivos **Log** de la aplicación.
* `public`: Este directorio contiene datos disponibles para los usuarios de la aplicación, tales como las hojas de estilo (`css`), imágenes, etc.
* `test`: Dentro de este directorio se encuentran todos los ficheros que nos ayudarán a realizar pruebas de testeo a la aplicación.
* `vendor`: Este directorio contiene la tercera parte del código, tales como plugins y gemas.
* `Gemfile`: Junto al fichero `Gemfile.lock`, nos permiten especificar qué gemas son necesarias para nuestra aplicación.

## 3. Primera página en Rails

### 3.1. Generación del Controlador

Cuando accedemos a cualquier aplicación, ya sea de escritorio o web, por lo general lo primero que vemos es algún mensaje de bienvenida. Para hacer lo mismo en nuestra aplicación debemos crear como mínimo un controlador y una vista.

Para crear un controlador, debemos ejecutar el **generador de controladores** y especificar el nombre de este y luego una acción. Por ejemplo, si queremos que nuestro controlador se llame `dashboard` y la acción `index`, debemos ejecutar (dentro de la carpeta de nuestro proyecto) lo siguiente:

```
rails generate controller dashboard index
```

O también:

```
rails g controller dashboard index
```

Con esto, Rails creará una serie de archivos y añadirá una ruta por ti, donde los archivos más importantes serán el **Controlador** de nombre `dashboard_controller.rb` (alojado en la ruta `app/controllers`) y la **Vista** de nombre `index.html.erb` (alojada en `app/views/dashboard`).

Para acceder a la **Vista** que acabamos de crear, debemos arrancar el servidor con el comando `rails server` y acceder a la ruta [http://localhost:3000/dashboard/index](http://localhost:3000/dashboard/index).

No olvidar:
* `dashboard`: Corresponde al **Controlador**.
* `index`: Corresponde a la **acción** o **método**.

### 3.2. Estableciendo nuestra página principal

El propósito de la **Vista** que acabamos de generar es que podamos visualizarla en nuestra página de inicio, es decir, en la URL [http://localhost:3000](http://localhost:3000). Para lograr esta hazaña, lo primero que debemos hacer es dirigirnos a la carpeta `routes` de nuestro proyecto y acceder al fichero `routes.rb`, donde encontraremos algo como lo siguiente:

``` rb
Rails.application.routes.draw do
  get 'dashboard/index'
end
```

Aquí debemos cambiar lo que se encuentra en la segunda línea por:

``` rb
root 'dashboard#index'
```

Lo que le permitirá a Rails asociar las peticiones de la raíz de la aplicación a la acción `index` del **Controlador** `dashboard`.

Si ahora ejecutamos el servidor (`rails server`) y accedemos a la dirección [http://localhost:3000](http://localhost:3000) veremos la misma **Vista** que antes podíamos ver en [http://localhost:3000/dashboard/index](http://localhost:3000/dashboard/index).

|     |     |
|:----|----:|
| [< Lección N°6](https://nisoto.github.io/rails-vi-desarrollo-web/){: .btn .btn-info} | [Inicio >](https://nisoto.github.io/blog/){: .btn .btn-info} |
