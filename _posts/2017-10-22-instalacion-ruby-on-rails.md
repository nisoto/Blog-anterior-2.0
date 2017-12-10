---
layout: post
title: "Instalación y configuración de Ruby on Rails"
date: 2017-10-22
excerpt: "Segundo capítulo del curso de Ruby on Rails 5"
tags: [ruby, ruby-on-rails]
---

En este segundo capítulo del curso de Ruby on Rails aprenderás a instalar Rails (valga la redundancia) y a cómo crear una aplicación para posteriormente configurar el entorno de desarrollo sobre el que estarás trabajando a lo largo de este curso.

Es importante mencionar que antes de instalar Ruby on Rails en tu computadora, primero debes tener instalado el lenguaje de programación Ruby, por lo que si aún no lo has hecho, has clic [aquí](https://nisoto.github.io/instalacion-ruby/). Una última cosa (y creo que más importante que la anterior) es que la instalación (tanto de Ruby como Ruby on Rails) se desarrolla en un computador con una distribución Linux, específicamente Ubuntu en su versión 14.04 LTS, por lo que si posees otro sistema operativo (como Windows o Mac OS) te invito a que visites [gorails](https://gorails.com/setup/ubuntu/14.04) y selecciones el sistema operativo y versión adecuada para ti.

# Instalación de Ruby on Rails

Lo primero que debemos hacer es instalar el lenguaje Ruby (más arriba, o dentro de mi blog, encontrarás el enlace al post). Una vez que tengas instalado Ruby de manera correcta, el siguiente paso es instalar NodeJS, el cual es muy importante ya que nos permitirá utilizar CoffeeScript y Asset Pipeline (más adelante veremos esos términos así que no te preocupes si no entiendes por el momento):

{% highlight ca65 %}
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
sudo apt-get install -y nodejs
{% endhighlight %}

Por último, instalamos la gema de Rails:

{% highlight ca65 %}
gem install rails -v 5.0.1
{% endhighlight %}

Si instalaste Ruby mediante `rbenv` deberás ejecutar el siguiente comando una vez que se haya completado el proceso de instalación de la gema de rails:

{% highlight ca65 %}
rbenv rehash
{% endhighlight %}

Para corroborar que la instalación se haya realizado de forma exitosa, ejecuta el siguiente comando:

{% highlight ca65 %}
rails -v
# Rails 5.0.1
{% endhighlight %}

# Instalación de un gestor de bases de datos

Rails por defecto utiliza sqlite3 como gestor de bases de datos, por lo que lo más probable es que quieras utilizar algún gestor más robusto como MySQL o PostgreSQL. En este apartado instalaremos y configuraremos PostgreSQL:

[Capítulo Anterior](https://nisoto.github.io/introduccion-ruby-on-rails/){: .btn .btn-success}
