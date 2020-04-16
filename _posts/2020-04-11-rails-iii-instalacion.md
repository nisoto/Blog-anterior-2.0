---
layout: post
title: "Ruby on Rails III: Instalación"
date: 2020-04-11
excerpt: "Capítulo N°3 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Instalación de Ruby

Antes de Ruby, debemos instalar algunas dependencias:

```
sudo apt install curl
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update
sudo apt-get install git-core zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn
```

Ahora si podemos proceder con el lenguaje de programación:

```
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.7.1
rvm use 2.7.1 --default
ruby -v
```

**Referencia**: [gorails.com](https://gorails.com/setup/ubuntu/18.04). Ubuntu 18.04, apartado **Installing Ruby**.

## 2. Instalación de Rails

Una vez instalado Ruby, ejecutamos lo siguiente para instalar Rails:

```
gem install rails -v 6.0.2.2
rails -v
```

**Referencia**: [gorails.com](https://gorails.com/setup/ubuntu/18.04). Ubuntu 18.04, apartado **Installing Rails**.

## 3. Instalación de un editor de código (IDE)

Un editor de texto o código nos será de gran utilidad para trabajar en nuestro proyecto. En este caso utilizaremos **Atom**:

```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packagecloud.io/AtomEditor/atom/gpgkey -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main"
sudo apt install atom
```

**Referencia**: [Atom](https://linuxize.com/post/how-to-install-atom-text-editor-on-ubuntu-18-04/). Ubuntu 18.04.

## 4. Primeros pasos en Ruby on Rails

### 4.1. Creación de nuestro proyecto

Una vez instalado Ruby y Ruby on Rails en nuestra computadora crearemos un nuevo proyecto, para lo cual ejecutaremos el siguiente comando en la terminal:

```
rails new myapp
```

Con esto, Rails inmediatamente comenzará a crear varias carpetas y archivos necesarios para nuestro proyecto y por último, instalará las **Gemas** por default.

Seguramente te estarás preguntando **¿Qué diablos es una gema?** y la respuesta es simple: en Rails, las gemas (gems en inglés) son el equivalente a las librerías en otros lenguajes, es decir, código predefinido, las cuales se alojan en un fichero llamado **Gemfile**.

Un punto importante a considerar a la hora de crear un proyecto en Rails es la **base de datos** que vamos a utilizar. En nuestro caso no hemos especificado ninguna, por lo que Rails por defecto utilizará **sqlite3** (que ya viene instalada en nuestro sistema operativo). Si quisiéramos utilizar otra (como MySQL por ejemplo) debemos agregar lo siguiente al momento de crear un nuevo proyecto:

```
rails new myapp -d mysql
```

O, si queremos utilizar PostgreSQL:

```
rails new myapp -d postgresql
```

### 4.2. Ejecución de nuestra aplicación

Una vez creado nuestro proyecto, para ingresar a su directorio ejecutamos el siguiente comando:

```
cd myapp
```

Y luego utilizamos:

```
rails server
```

Para iniciar el servidor.

Para ver tu aplicación en acción, abre tu navegador preferido y accede a [http://localhost:3000](http://localhost:3000), donde deberías ver algo como lo siguiente:

![HolaRails]({{ site.baseurl }}/assets/img/hirails!.png)

### 4.3. Principales comandos de Rails

Rails cuenta con una serie de comandos que serán de gran utilidad a lo largo de la construcción de nuestra aplicación. A continuación algunos:

* `rails generate` o `rails g`: Genera ficheros tales como assets, model, controller, helper, migration y scaffold, entre otros.
* `rails console` o `rails c`: Llama a la consola de ruby para manipular las clases del proyecto.
* `rails server` o `rails s`: Inicia el servidor de rails que, por defecto, corre en el **puerto 3000**.
* `rails dbconsole` o `rails db`: Se conecta a la base de datos con la que estamos trabajando.

### 4.4. Subiendo nuestro proyecto a Github

En el capítulo anterior creamos nuestra cuenta de Github y nuestro primer repositorio, en el cual subiremos el proyecto de Rails que acabamos de generar.

![PrimerRepo]({{ site.baseurl }}/assets/img/PrimerRepo.jpg)

Para subir dicho proyecto a la plataforma, debemos seguir los siguientes pasos (de manera ordenada):

**Primero**, debemos inicializar nuestro repositorio:

```
git init
```

**Luego**, subir al estado intermedio de Git el proyecto:

```
git add -A
```

* **Nota 1**: El comando `-A` subirá todas las carpetas y ficheros que se encuentran dentro la carpeta de nuestro proyecto de Rails.

**No olvidemos** añadir un comentario a lo que estamos subiendo:

```
git commit -m "first commit"
```

**Finalmente**, realizamos la vinculación con el repositorio de Github (para eso la llave SSH) y subimos los cambios con `git push`:

```
git remote add origin git@github.com:nisoto/Prueba.git
git push -u origin master
```

* **Nota 2**: Para las siguientes ocasiones, solo basta con ejecutar `git push` para subir los cambios.

|     |     |
|:----|----:|
| [< Lección N°2](https://nisoto.github.io/rails-ii-control-de-versiones/){: .btn .btn-info} | [Lección N°4 >](https://nisoto.github.io/rails-iv-ruby-en-detalle/){: .btn .btn-info} |
