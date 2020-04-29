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

## 3. Instalación y configuración de Git

En Sistemas Operativos como Ubuntu o Mac OS Git ya viene instalado, por lo que solo debemos configurarlo. Para ello abrimos la terminal y tecleamos lo siguiente:

```
$ git config --global user.name "YOUR NAME"
$ git config --global user.email "YOUR@EMAIL.com"
```

En **YOUR NAME** debemos colocar nuestro nombre y en **YOUR@EMAIL.COM** el correo que utilizamos para nuestra cuenta de Github.

## 4. Flujo de trabajo

Git está compuesto por tres **estados** o **árboles** en los que se pueden encontrar los archivos de nuestro proyecto:

1. **Working directory**: O directorio de trabajo en español, contiene nuestro archivo o conjunto de archivos del proyecto.
2. **Staging area**: O área de preparación en español, también es conocida como **index** y actúa como una zona intermedia en donde escogeremos qué archivos están listos para pasar al siguiente estado y/o cuales no lo están por el momento.
3. **Git directory**: O directorio de Git en español, también se le conoce como **head** y corresponde al repositorio donde se encuentra el registro de todo nuestro proyecto (commits).

![EstadosGit]({{ site.baseurl }}/assets/img/EstadosGit.jpg)

Aquí es donde aparece una nueva palabra: **commit**. Un commit corresponde a la acción de guardar o subir un archivo o conjunto de archivos al **Directorio de Git** (head).

## 5. Primeros commits y viajes en el tiempo

### 5.1. `git init`

Se utiliza para inicializar un repositorio local.

```
$ git init
```

### 5.2. `git add`

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

### 5.3. `git commit -m "mensaje"`

Subirá al **directorio de Git** (head) los archivos que se encuentran en el **área de preparación** (index), agregando un comentario para poder indentificarlo.

```
$ git commit -m "Primer commit"
```

### 5.4. `git status`

Nos muestra el estado del **directorio de trabajo** y el **área de preparación** (qué cambios se han organizado, cuáles no y qué archivos están siendo rastreados por Git).

```
$ git status
```

### 5.5. `git log`

Nos muestra una lista con todos los commits realizados con su respectiva información (mensaje).

```
$ git log
commit 7fd525835c8c0359ea13fd982a04251d61832ab6 (HEAD -> master)
Author: YOUR NAME <YOUR@EMAIL.COM>
Date:   Sat Apr 25 21:22:20 2020 -0400

    Segundo commit
    
commit 7827ceb120fbc23a8bc18e1e9c680ce1f731fed2
Author: YOUR NAME <YOUR@EMAIL.COM>
Date:   Mon Apr 20 18:58:58 2020 -0400

    Primer commit
```

### 5.6. `git checkout`

Con este comando podemos **viajar** a través de nuestros commits o ramas (más adelante veremos en detalle lo que son las **ramas**).

```
$ git checkout 7fd525835c8c0359ea13fd982a04251d61832ab6
```

Si queremos regresar al último commit, utilizamos `master`:

```
$ git checkout master
```

**Importante**: `master` siempre corresponderá al último commit que nosotros hayamos generado, mientras que el `head` podrá variar dependiendo de lo que le indiquemos por medio del comando `checkout`.

## 6. Reset

El comando `reset` funciona de manera similar a `checkout`, con la diferencia de que este **elimina** los commits a su paso. Existen 3 niveles o tipos de borrado:

### 6.1. Reset soft

Este tipo de `reset` nos permite viajar a un commit en específico, borrando los posteriores a este. Sin embargo, mantiene nuestro directorio de trabajo intacto.

```
$ git reset --soft 7827ceb120fbc23a8bc18e1e9c680ce1f731fed2
```

### 6.2. Reset mixed

Funciona de manera similar al anterior (soft), borrando también los archivos que se encuentren en el área de preparación (index). Tampoco se mete con nuestro directorio de trabajo.

```
$ git reset --mixed 7827ceb120fbc23a8bc18e1e9c680ce1f731fed2
```

### 6.3. Reset hard

Como su nombre lo indica, borra absolutamente todo lo que hay después del commit al que queremos viajar, afectando incluso nuestro directorio de trabajo.

```
$ git reset --hard 7827ceb120fbc23a8bc18e1e9c680ce1f731fed2
```

## 7. Ramas y fusiones

Una **rama** en Git vendría siendo una especie de **línea de tiempo** de un proyecto, la cual se construye mediante nuestros commits.

Cuando nosotros inicializamos nuestro repositorio local con el comando `git init`, Git internamente genera la rama principal o **rama master**, es decir, la línea de tiempo por defecto en la que estaremos trabajando.

Las ramas son utilizadas por lo general para desarrollar funcionalidades aisladas unas de otras (como el testing, por ejemplo).

### 7.1. Ramas

Crear una nueva rama en Git es bastante sencillo:

```
$ git branch testing
```

Ten en cuenta que al momento de crear una nueva rama, ésta contará con **los mismos commits** que la rama **master**.

El comando `git branch` a secas nos permite listar todas las ramas existentes, marcando con un **asterisco** en la que estemos actualmente:

```
$ git branch
* master
  testing
```

Si tienes buena memoria, recordarás que `checkout` nos permite viajar entre commits y **ramas**, por lo que si queremos cambiarnos a la rama **testing**, debemos hacer lo siguiente:

```
$ git checkout testing
```

Por lo tanto, si ejecutamos el comando `git branch`, el asterisco debería estar sobre esta nueva rama:

```
$ git branch
  master
* testing
```

Si por alguna razón queremos **borrar** la rama que hemos creado (porque ya no nos sirve o simplemente porque los cambios en esta línea de tiempo contienen muchos errores), debemos posicionarnos primeramente en la rama principal y ejecutar lo siguiente:

```
$ git branch -D testing
```

### 7.2. Fusiones

Una **fusión** en Git consiste en la unión de dos ramas, proceso que consta de 2 pasos muy importantes:

1. Situarnos en la rama que va a absorver a la otra.
2. Ejecutar la fusión.

Si tomamos el ejemplo anterior, fusionaremos la rama **master** con **testing**, siguiendo los pasos respectivos:

```
$ git checkout master
$ git merge testing
```

Al hacer un `git log` nos podremos dar cuenta que la rama master también cuenta con los commits de la rama que acabamos de absorver.

## 8. Github

Github corresponde a un sitio que nos permite contar con las virtudes de Git como sistema de control de versiones pero en Internet, dándonos ciertas ventajas como compartir nuestro trabajo y/o trabajar con más personas.

Tanto Github como otros sitios que cumplen la misma función (Gitlab o Bitbucket, por ejemplo) se han convertido hoy en día en **redes sociales** para los programadores ya que como se especificó anteriormente, nos permiten compartir nuestro trabajo (muchas empresas revisan nuestros perfiles de Github para tener conocimiento de nuestros trabajos realizados) y trabajar con más personas (por ejemplo, un equipo de desarrolladores de software).

Es importante considerar que Github se sumaría al **flujo de trabajo** de Git como un **cuarto estado** o árbol:

![EstadosGit2]({{ site.baseurl }}/assets/img/EstadosGit2.jpg)

### 8.1. Registro y configuración de la llave SSH

Crear una cuenta en Github es bastante sencillo, solo debemos ir a la [página](https://github.com/) y hacer clic en **Sign up**, donde se nos pedirá un usuario, correo y contraseña.

Una vez creada nuestra cuenta, el siguiente paso es enlazarla con Git y para ello será necesario crear una llave SSH. Nos dirigimos a la terminal y ejecutamos lo siguiente:

```
$ ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"
```

Este comando generará dicha llave, la cual debemos copiar dentro de nuestra cuenta de Github. Para visualizarla ejecutamos:

```
$ cat ~/.ssh/id_rsa.pub
```

Comando que nos mostrará a través de la terminal la llave, que debemos copiar en la ruta **Settings > SSH and GPG keys > New SSH key**. Para verificar la correcta vinculación, basta con ejecutar en la terminal:

```
$ ssh -T git@github.com
```

Y se debería desplegar un mensaje como el siguiente:

```
Hi excid3! You've successfully authenticated, but GitHub does not provide shell access.
```

### 8.2. Primer repositorio

Tal como lo hemos venido diciendo en los apartados anteriores, un **repositorio** o "repo" es un directorio donde se almacenan los archivos de un proyecto, el cual puede estar ubicado en el almacenamiento de Github o localmente en nuestra computadora (Git). En este directorio podemos almacenar archivos de código, imágenes, audios o todo lo relacionado a un proyecto de cualquier tipo.

Para crear un repositorio en Github, debemos ir a la pestaña **"+"** ubicada en la barra superior de la aplcación y hacer clic en **New repository**, lo cual nos desplegará un formulario con algunos datos a completar:

![CrearRepositorio]({{ site.baseurl }}/assets/img/CrearRepositorio.jpg)

Como puedes ver, el único campo obligatorio corresponde al **nombre** del repositorio. Una vez hayamos completado los datos, hacemos clic en **Create repository** y listo.

|     |     |
|:----|----:|
| [< Lección N°5](https://nisoto.github.io/rails-v-ruby-avanzado/){: .btn .btn-info} | [Lección N°7 >](https://nisoto.github.io/rails-vii-desarrollo-web/){: .btn .btn-info} |
