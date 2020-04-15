---
layout: post
title: "Ruby on Rails IV: ¡Por fin Rails!"
date: 2020-04-15
excerpt: "Capítulo N°4 del curso de Ruby on Rails"
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
