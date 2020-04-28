---
layout: post
title: "Ruby on Rails VI: Git"
date: 2020-04-22
excerpt: "Capítulo N°6 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ¿Qué es Git?

Git corresponde a un **sistema de control de versiones** desarrollado por Linus Torvalds.

No olvidemos que cuando hablamos de **control de versiones**, nos referimos a la gestión de los diversos cambios que se realizan sobre un proyecto (subir código a la nube, añadir alguna parte o simplemente editar algo que no funciona correctamente, entre otros).

Por lo tanto, un sistema de control de versiones serían todas las herramientas que nos permiten hacer esas modificaciones antes mencionadas sobre nuestro trabajo, haciendo más fácil la administración de las distintas versiones.

## 2. Git en el mundo

Git es usado por grandes empresas ya que esta herramienta permite que muchas de las aplicaciones que usamos hoy en día sean tal y como las conocemos. Algunas de estas empresas, que de seguro las conocerás, son las siguientes:

* Facebook
* Twitter
* Netflix
* Google
* LikedIn

Estas corresponden a empresas que venden productos de Internet, por lo que hoy en día su uso es pan de cada día. Sin embargo, Git también tiene presencia en los equipos de trabajo que desarrollan sistemas operativos para los dispositivos, tales como:

* Microsoft
* Android
* Linux

Incluso el software que nos ayuda a crear más software utiliza Git:

* Ruby on Rails (Framework de Ruby para el desarrollo web)
* PostgreSQL (Gestor de Base de Datos)
* Eclipse (IDE para crear aplicaciones en Java)

Y no cabe duda de que hay muchos otros ejemplos de equipos de trabajo que utilizan Git no solo en el desarrollo de software, sino también de contenido y productos profesionales.

## 3. Github

Github corresponde a un sitio que nos permite contar con las virtudes de Git como sistema de control de versiones pero en Internet, dándonos ciertas ventajas como compartir nuestro trabajo y/o trabajar con más personas.

Tanto Github como otros sitios que cumplen la misma función (Gitlab o Bitbucket, por ejemplo) se han convertido hoy en día en **redes sociales** para los programadores ya que como se especificó anteriormente, nos permiten compartir nuestro trabajo (muchas empresas revisan nuestros perfiles de Github para tener conocimiento de nuestros trabajos realizados) y trabajar con más personas (por ejemplo, un equipo de desarrolladores de software).

## 4. Instalación y configuración de Git

En Sistemas Operativos como Ubuntu o Mac OS Git ya viene instalado, por lo que solo debemos configurarlo. Para ello abrimos la terminal y tecleamos lo siguiente:

```
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR@EMAIL.com"
```

En **YOUR NAME** debemos colocar nuestro nombre y en **YOUR@EMAIL.COM** el correo que utilizamos para nuestra cuenta de Github.

## 5. Flujo de trabajo

Git está compuesto por tres **estados** o **árboles** en los que se pueden encontrar los archivos de nuestro proyecto.

1. **Working directory**: O directorio de trabajo en español, contiene nuestro archivo o conjunto de archivos del proyecto.
2. **Staging area**: O área de preparación en español, también es conocida como **index** y actúa como una zona intermedia en donde escogeremos qué archivos están listos para pasar al siguiente estado y/o cuales no lo están por el momento.
3. **Git directory**: O directorio de Git en español, también se le conoce como **head** y corresponde al repositorio donde se encuentra el registro de todo nuestro proyecto (commits).

Aquí es donde aparece una nueva palabra: **commit**. Un commit corresponde a la acción de guardar o subir un archivo o un conjunto de archivos al **Directorio de Git** (head).

![EstadosGit]({{ site.baseurl }}/assets/img/EstadosGit.jpg)

## 6. Comandos Git

### 6.1. `git init`

Se utiliza para inicializar un repositorio local.

```
$ git init
```

### 6.2. `git add`

Nos permite subir un archivo desde el **directorio de trabajo** al **área de preparación** (index).

```
$ git add index.html
```

Si queremos subir todos los archivos del directorio de trabajo, utilizamos `-A`:

```
$ git add -A
```

Para devolver al directorio de trabajo un archivo que se encuentra en el área intermedia, utilizamos `rm --cached`:

```
$ git rm --cached index.html
```

### 6.3. `git commit -m "mensaje"`

Subirá al **directorio de Git** (head) los archivos que se encuentran en el área intermedia o de preparación (index), agregando un comentario para poder indentificarlo.

```
$ git commit -m "primer commit"
```

### 6.4. `git status`

Nos muestra el estado del **directorio de trabajo** y el **área de preparación** (qué cambios se han organizado, cuáles no y qué archivos están siendo rastreados por Git).

```
$ git status
```

### 6.5. `git log`

Nos muestra una lista con todos los commits realizados con su respectiva información (mensaje).

```
$ git log
commit 7fd525835c8c0359ea13fd982a04251d61832ab6
Author: YOUR NAME <YOUR@EMAIL.COM>
Date:   Sat Apr 25 21:22:20 2020 -0400

    Primer commit
```

### 6.6. `git checkout`

Con este comando podemos **viajar** a través de nuestros commits o ramas (más adelante veremos lo que es una **rama**).

```
$ git checkout 7fd525835c8c0359ea13fd982a04251d61832ab6
```

Si queremos volver al último commit, utilizamos `master`:

```
git checkout master
```

|     |     |
|:----|----:|
| [< Lección N°5](https://nisoto.github.io/rails-v-ruby-avanzado/){: .btn .btn-info} | [Lección N°7 >](https://nisoto.github.io/rails-vii-desarrollo-web/){: .btn .btn-info} |
