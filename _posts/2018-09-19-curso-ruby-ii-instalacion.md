---
layout: post
title: "Curso de Ruby II: Instalación"
date: 2018-09-19
excerpt: "Capítulo N°2 del curso de Ruby"
tags: [ruby]
---

# Instalación

## Linux y Mac OS

Sistemas Operativos como Linux y Mac OS ya poseen una versión de Ruby preconfigurada, por lo que no será necesario instalar este lenguaje a menos que tengas una versión antigua (inferior a 2.0) ya que en ese caso conviene actualizar:

### Ubuntu

Para el caso de Ubuntu (Linux), lo recomendable es instalar Ruby por medio de **rvm**, lo cual nos permitirá definir qué versión de Ruby queremos utilizar:

```
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.5.1
rvm use 2.5.1 --default
gem install bundler
```

### Mac OS

```
brew install rbenv ruby-build
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
source ~/.bash_profile
rbenv install 2.5.1
rbenv global 2.5.1
```

Cabe destacar que los comandos de instalación de Ruby en Ubuntu y Mac OS han sido extraídos de **GoRails**, tomando en cuenta las últimas versiones de estos Sistemas Operativos (18.10 y 10.14 respectivamente), por lo que si posees alguna versión más antigua de éstos, te recomiendo visitar esta [página](https://gorails.com/setup/ubuntu/18.10).

## Windows

Si utilizas Windows (cualquiera sea su versión) podrás intalar este lenguaje desde [RubyInstaller](https://rubyinstaller.org/) o [RailsInstaller](http://railsinstaller.org/en), la opción que elijas dependerá de tus necesitades personales (por ejemplo, si estás interesado en aprender Ruby on Rails conviene instalar RailsInstaller).

Podemos verificar la correcta instalación de este lenguaje (cualquiera sea tu Sistema Operativo) abriendo la terminal y escribiendo el siguiente comando:

```
$ ruby -v
ruby 2.5.1p57 (2018-03-29 revision 63029) [x64-mingw32]
```

# Consola Interactiva de Ruby (IRB)

Una vez instalado Ruby, sólo debes escribir **irb** en la terminal para ingresar a la **"Consola interactiva"** que incluye este lenguaje:

```ruby
$ irb
irb(main):001:0>
```

Todo lo que escribamos luego de este comando será evaluado como código de Ruby. Escribiremos el clásico "Hola Mundo" por pantalla:

```ruby
irb(main):001:0> puts "Hola Mundo"
```

Si ahora presionamos la tecla **Enter** el mensaje que acabamos de escribir será mostrado por pantalla, e inmediatamente la consola quedará a la espera de una siguiente instrucción:

```ruby
irb(main):001:0> puts "Hola Mundo"
Hola Mundo
=> nil
irb(main):002:0>
```

La Consola Interactiva de Ruby sirve bastante si estás aprendiendo a utilizar este lenguaje o si quieres realizar algunas pruebas, pero a la hora de desarrollar programas más elaborados, lo recomendable es utilizar algún editor de texto como **Sublime Text** y luego ejecutar dicho programa por consola utilizando el siguiente comando:

```
$ ruby hola_mundo.rb
```

Donde **hola_mundo** corresponde al nombre del programa y `.rb` es la extensión de Ruby (así como `.c` lo es para el lenguaje C y `.py` lo es para Python).

|     |     |
|:----|----:|
| [< Introducción](https://nisoto.github.io/curso-ruby-i-introduccion/){: .btn .btn-info} | [Variables >](https://nisoto.github.io/curso-ruby-iii-variables/){: .btn .btn-info} |
