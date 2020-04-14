---
layout: post
title: "Ruby on Rails III: Instalación"
date: 2020-04-14
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

## 2. Instalación de Rails

Una vez instalado Ruby, ejecutamos lo siguiente para instalar Rails:

```
gem install rails -v 6.0.2.2
rails -v
```

## 3. Primeros pasos en Ruby on Rails

### 3.1. Creación de nuestro proyecto

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

### 3.2. Ejecución de nuestra aplicación

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
