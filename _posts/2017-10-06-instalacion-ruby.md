---
layout: post
title: "Instalación de Ruby"
date: 2017-10-06
excerpt: "Segundo capítulo del curso de Ruby"
tags: [ruby]
---

En este segundo capítulo del curso de Ruby aprenderás a instalar Ruby en tu computadora y a utilizar la famosa **"Consola Interactiva de Ruby"** (en inglés Interactive Ruby Shell, que suele abreviarse como **IRB** o **irb**) la cual viene incluida en dicha instalación. Cabe destacar que la instalación se desarrolla en un computador con una distribución Linux, específicamente Ubuntu en su versión 14.04 LTS, por lo que si posees otro sistema operativo (como Windows o Mac OS) te invito a que visites [gorails](https://gorails.com/setup/ubuntu/14.04) y selecciones el sistema operativo y versión adecuada para ti.

# Instalación

Lo primero que debemos hacer es instalar algunas dependencias para Ruby:

{% highlight ca65 %}
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev nodejs
{% endhighlight %}

Ahora podemos comenzar con la instalación de Ruby, donde tendremos 3 métodos distintos: **rbenv**, **rvm** o de **fuente**. Cada uno tiene sus propias ventajas, aunque la mayoría de los programadores hoy en día prefiere hacerlo mediante rbenv por sobre rvm y de fuente (aquí verás las 3 formas). Personalmente te recomiendo que lo hagas mediante rbenv si eres nuevo en el mundo de este lenguaje.

## Instalación con rbenv

Instalar con rbenv es un proceso muy fácil que consta de sólo 2 pasos: instalar `rbenv` y luego `ruby-build`.

{% highlight ca65 %}
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

rbenv install 2.4.0
rbenv global 2.4.0
ruby -v
{% endhighlight %}

## Instalación con rvm

La instalación con rvm es un poco más sencilla que con `rbenv`:

{% highlight ca65 %}
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.4.0
rvm use 2.4.0 --default
ruby -v
{% endhighlight %}

## Instalación de fuente

Posiblemente la instalación menos útil de Ruby es desde el ódigo fuente. De todas maneras dejaré los pasos:

{% highlight ca65 %}
cd
wget http://ftp.ruby-lang.org/pub/ruby/2.4/ruby-2.4.0.tar.gz
tar -xzvf ruby-2.4.0.tar.gz
cd ruby-2.4.0/
./configure
make
sudo make install
ruby -v
{% endhighlight %}

Una vez que hayas instalado Ruby utilizando cualquiera de los 3 métodos anteriores, el último paso es instalar Bundler:

{% highlight ca65 %}
gem install bundler
{% endhighlight %}

Si instalaste Ruby mediante **rbenv** deberás ejecutar el siguiente comando después de haber instalado Bundler:

{% highlight ca65 %}
rbenv rehash
{% endhighlight %}

# Consola Interactiva de Ruby

Una vez instalado Ruby, sólo debes abrir la terminal (`Ctrl` + `Alt` + `T`) y escribir irb para ingresar a la **"Consola Interactiva"** que incluye este lenguaje:

{% highlight ca65 %}
irb
irb(main):001:0>
{% endhighlight %}

A modo de ejemplo crearemos nuestro primer programa, el típico "Hola Mundo" por pantalla:

{% highlight ca65 %}
irb(main):001:0> puts "Hola Mundo"
{% endhighlight %}

Si ahora presionas la tecla **Enter** te darás cuenta de que el mensaje que acabas de escribir será mostrado por pantalla, e inmediatamente la consola quedará a la espera de una siguiente instrucción:

{% highlight ca65 %}
irb(main):001:0> puts "Hola Mundo"
Hola Mundo
=> nil
irb(main):002:0>
{% endhighlight %}

La consola interactiva de Ruby te servirá bastante si estás aprendiendo a utilizar este lenguaje o si quieres realizar pruebas, pero a la hora de desarrollar programas más elaborados, lo recomendable es utilizar algún editor de texto como sublime text o atom, y luego ejecutar dicho programa por consola utilizando el siguiente comando:

{% highlight ca65 %}
ruby hola_mundo.rb
{% endhighlight %}

Donde hola_mundo corresponde al nombre del programa y `.rb` es la extensión de Ruby (así como `.c` lo es para el lenguaje C y `.py` lo es para Python).

|     |     |     |
|:----|:---:|----:|
| [<](https://nisoto.github.io/introduccion-ruby/){: .btn .btn-info} | [Volver](https://nisoto.github.io/curso-ruby/){: .btn .btn-info} | [>](https://nisoto.github.io/variables-ruby/){: .btn .btn-info} |
