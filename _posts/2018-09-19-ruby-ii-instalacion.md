---
layout: post
title: "Ruby II: Instalación"
date: 2018-09-19
excerpt: "Capítulo N°2 del curso de Ruby"
tags: [ruby]
---

# Hola

Amigos.

Si utilizas Linux o Mac, ya tienes instalado Ruby ya que estos Sistemas Operativos ya vienen con una versión de Ruby preconfigurada.

Cualquier versión servirá, siempre y cuando sea superior a 2

Si utilizas Windows

Ruby Installer o Rails Installer

Si estás interesado en aprender Ruby on Rails, conviene instalar RailsInstaller

Conviene siempre instalar la última versión disponible!

RubyInstaller tiene la ventaja de que se actualiza más rápido

{% highlight ruby %}
$ ruby -v
ruby 2.5.1p57 (2018-03-29 revision 63029) [x64-mingw32]
{% endhighlight %}

# Consola Interactiva de Ruby (IRB)

Una vez instalado Ruby, sólo debes escribir **irb** en la terminal para ingresar a la **"Consola interactiva"** que incluye este lenguaje:

{% highlight ruby %}
$ irb
irb(main):001:0>
{% endhighlight %}

Todo lo que escribamos luego de este comando será evaluado como código de Ruby. Escribiremos el clásico "Hola Mundo" por pantalla:

{% highlight ruby %}
irb(main):001:0> puts "Hola Mundo"
{% endhighlight %}

Si ahora presionamos la tecla **Enter** el mensaje que acabamos de escribir será mostrado por pantalla, e inmediatamente la consola quedará a la espera de una siguiente instrucción:

{% highlight ruby %}
irb(main):001:0> puts "Hola Mundo"
Hola Mundo
=> nil
irb(main):002:0>
{% endhighlight %}

La Consola Interactiva de Ruby sirve bastante si estás aprendiendo a utilizar este lenguaje o si quieres realizar algunas pruebas, pero a la hora de desarrollar programas más elaborados, lo recomendable es utilizar algún editor de texto como **Sublime Text** y luego ejecutar dicho programa por consola utilizando el siguiente comando:

{% highlight ruby %}
$ ruby hola_mundo.rb
{% endhighlight %}

Donde **hola_mundo** corresponde al nombre del programa y `.rb` es la extensión de Ruby (así como `.c` lo es para el lenguaje C y `.py` lo es para Python).
