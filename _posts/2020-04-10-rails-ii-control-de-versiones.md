---
layout: post
title: "Ruby on Rails II: Control de Versiones"
date: 2020-04-10
excerpt: "Capítulo N°2 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Control de Versiones

### 1.1. ¿Qué es?

Un Control de Versiones (VCS por sus siglas en inglés) es un sistema que registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo, de modo que podamos recuperar versiones específicas más adelante.

### 1.2. Características

Si eres diseñador gráfico o de web y quieres mantener cada versión de una imagen o diseño, usar un Sistema de Control de Versiones es una decisión muy acertada. Dicho sistema te permitirá:

* Regresar a versiones anteriores de tus archivos
* Regresar a una versión anterior del proyecto completo
* Comparar cambios a lo largo del tiempo
* Ver quién modificó por última vez algo que pueda estar causando problemas
* Ver quién introdujo un problema y cuándo
* Y mucho más

### 1.3. Tipos de VCS

Los Sistemas de Control de Versiones han ido evolucionando a lo largo del tiempo y podemos clasificarlos en 3 tipos:

#### 1. **Sistemas de Control de Versiones Locales**

Un método de control de versiones usado por muchas personas consiste en copiar los archivos a otro directorio, lo cual es tremendamente propenso a errores (como olvidar en qué directorio te encuentras y guardar accidentalmente en el archivo equivocado o sobreescribir archivos que no querías, entre otros). Para afrontar este problema los programadores desarrollaron VCS Locales que contenían una simple base de datos, en la que se llevaba el registro de todos los cambios realizados a los archivos.

![VCS-Local]({{ site.baseurl }}/assets/img/VCS-Local.png)

Una de las herramientas de control de versiones más popular fue un sistema llamado **RCS**, que todavía podemos encontrar en muchas de las computadoras actuales.

#### 2. **Sistemas de Control de Versiones Centralizados**

El problema con el que se encuentran las personas es que necesitan colaborar con otros en el desarrollo de sistemas, es por ello que los Sistemas de Control de Versiones Centralizados (CVCS por sus siglas en inglés) fueron implementados para solucionar este inconveniente. Estos sistemas (como CVS, Subversion y Perforce) tienen un único servidor que contiene todos los archivos versionados y varios clientes que descargan los archivos desde ese lugar central. Este ha sido el estándar para el control de versiones por muchos años.

![VCS-Centralizado]({{ site.baseurl }}/assets/img/VCS-Centralizado.png)

Esta configuración ofrece muchas ventajas, especialmente frente a VCS Locales. Por ejemplo, todas las personas saben hasta cierto punto en qué están trabajando los otros colaboradores del proyecto. Los administradores tienen control detallado sobre qué puede hacer cada usuario y es mucho más fácil administrar un CVCS que tener que lidiar con bases de datos locales.

Sin embargo, esta configuración también tiene serias desventajas:
* La más obvia es el punto único de fallo que representa el servidor centralizado ya que si este se cae durante una hora, entonces nadie podrá colaborar o guardar cambios en los archivos en los que hayan estado trabajando durante esa hora.
* Si el disco duro en el que se encuentra la base de datos central se corrompe y no se han realizado copias de seguridad adecuadamente, se perderá toda la información del proyecto, con excepción de las copias instantáneas que las personas tengan en sus máquinas locales.

Los VCS Locales sufren de este mismo problema: Cuando tienes toda la historia del proyecto en un mismo lugar, te arriesgas a perderlo todo.

#### 3. **Sistemas de Control de Versiones Distribuidos**

Los Sistemas de Control de Versiones Distribuidos (DVCS por sus siglas en inglés) ofrecen soluciones para los problemas que han sido mencionados anteriormente. En un DVCS (como Git, Mercurial, Bazaar o Darcs), los usuarios no solo descargan la última copia instantánea de los archivos, sino que se replica completamente el repositorio. De esta manera, si un servidor deja de funcionar y estos sistemas estaban colaborando a través de él, cualquiera de los repositorios disponibles en los clientes puede ser copiado al servidor con el fin de restaurarlo. Cada clon es realmente una copia completa de todos los datos.

![VCS-Distribuido]({{ site.baseurl }}/assets/img/VCS-Distribuido.png)

Además, muchos de estos sistemas se encargan de manejar numerosos repositorios remotos con los cuales pueden trabajar, de tal forma que puedes colaborar simultáneamente con diferentes grupos de personas en distintas maneras dentro del mismo proyecto. Esto permite establecer varios flujos de trabajo que no son posibles en sistemas centralizados, como pueden ser los modelos jerárquicos.

## 2. Github

Github corresponde a un Sistema de Control de Versiones que nos permite trabajar en colaboración con otras personas de todo el mundo, planificar proyectos y realizar un seguimiento del trabajo. Todo esto es almacenado en la nube.

Github es también uno de los repositorios online más grandes de trabajo colaborativo en todo el mundo.

Seguramente te preguntarás qué tiene que ver Github con Git y la respuesta es muy simple: **Git es el corazón de Github** y **Github el alma de Git**, es decir, Github corresponde a la parte centralizada de Git (recuerda que Git es un Sistema de Control de Versiones Distribuido).

![Github]({{ site.baseurl }}/assets/img/Github.jpg)

## 3. Configurando nuestro VCS

### 3.1. Registrarse en Github

Crear una cuenta en Github es bastante sencillo, solo debemos ir a la [página](https://github.com/) y hacer clic en **Sign up**, donde se nos pedirá un usuario, correo y contraseña.

### 3.2. Configuración de Git

En Sistemas Operativos como **Ubuntu** o **Mac OS** Git ya viene instalado, por lo que solo debemos configurarlo. Para ello abrimos la terminal y tecleamos lo siguiente:

```
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR@EMAIL.com"
```

En **YOUR NAME** debemos colocar nuestro nombre y en **YOUR@EMAIL.COM** el correo que utilizamos para nuestra cuenta de Github.

### 3.3. Habilitación de la llave SSH

Para crear nuestra llave SSH, la cual nos permitirá vincular nuestro equipo a Github, debemos ir a la terminal y ejecutar lo siguiente:

```
ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"
```

Solo nos queda copiar la llave generada en nuestra cuenta de Github, para ello ejecutamos el comando:

```
cat ~/.ssh/id_rsa.pub
```

Que nos mostrará a través de la terminal la llave generada, que debemos copiar en la ruta **Settings > SSH and GPG keys > New SSH key**. Para verificar la correcta vinculación, basta con ejecutar en la terminal:

```
ssh -T git@github.com
```

Lo cual debería desplegar un mensaje como el siguiente:

```
Hi excid3! You've successfully authenticated, but GitHub does not provide shell access.
```

### 3.4. Primer repositorio

Primero que todo, un **repositorio** o "repo" es un directorio donde se almacenan los archivos de un proyecto. Puede estar ubicado en el almacenamiento de Github o localmente en tu computadora. En esta carpeta podemos almacenar archivos de código, imágenes, audios o todo lo relacionado con el proyecto.

Para crear un repositorio en Github, debemos ir a la pestaña **"+"** ubicada en la barra superior de la aplcación y hacer clic en **New repository**, lo cual nos desplegará un formulario con algunos datos a completar:

![CrearRepositorio]({{ site.baseurl }}/assets/img/CrearRepositorio.jpg)

Como puedes ver, el único campo obligatorio corresponde al **nombre** del repositorio. Una vez completados los datos, hacemos clic en **Create repository** y listo.

## 4. Primeros pasos en Git

En este apartado veremos algunos de los comandos básicos de Git que nos serán útiles a lo largo de este curso:

* `git init`: Se utiliza para inicializar un repositorio.
* `git clone`: Nos permite clonar un repositorio.
* `git add`: Nos permite subir el trabajo realizado a un estado intermedio de git.
* `git commit -m "comentario"`: Se utiliza para especificar un comentario del trabajo realizado.
* `git pull`: Nos permite descargar la última versión del proyecto (ideal cuando estamos trabajando en equipo).
* `git push`: Nos permite subir al repositorio de Github los cambios realizados (ubicados en ese estado intermedio).
* `git status`: Nos muertra el estado del directorio de trabajo y el área de preparación (qué cambios se han organizado, cuáles no y qué archivos no están siendo rastreados por Git).

|     |     |
|:----|----:|
| [< Lección N°1](https://nisoto.github.io/rails-i-introduccion/){: .btn .btn-info} | [Lección N°3 >](https://nisoto.github.io/rails-iii-instalacion/){: .btn .btn-info} |
