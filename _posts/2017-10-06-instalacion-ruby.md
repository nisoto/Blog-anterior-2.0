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
