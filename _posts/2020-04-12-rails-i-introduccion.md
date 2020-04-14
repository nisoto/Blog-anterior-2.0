---
layout: post
title: "Ruby on Rails I: Introducción"
date: 2020-04-12
excerpt: "Capítulo N°1 del curso de Ruby on Rails"
tags: [rails]
---

## 1. ¿Qué se aprenderá?

* El lenguaje de programación **Ruby**.
* El Framework **Ruby on Rails** para construir aplicaciones web, utilizando el lenguaje de programación Ruby.
* A manejar las versiones de nuestro proyecto mediante un **Sistema de Control de Versiones** (Git).

## 2. Ruby

### 2.1. ¿Qué es?

Ruby es un **lenguaje de programación** creado por el programador japonés Yukihiro "Matz" Matsumoto, quien comenzó a trabajar en él en 1993 y lo presentó públicamente en 1995.

Este lenguaje está inspirado en Lisp, Perl, Smalltalk, Eiffel y Ada (todos estos lenguajes contribuyeron al diseño con el que está construido Ruby).

Busca ser natural y no simple, es decir, es muy expresivo ya que prefiere el inglés antes que la puntuación (esto significa que cuando te sientes a leer el código te será mucho más fácil saber lo que está pasando).

Es totalmente gratuito y no solo eso, también es libre para usarlo, copiarlo, modificarlo y distribuirlo.

### 2.2. Características

1. **Es interpretado**, es decir, no existe un compilador ya parte del instalador incluye un intérprete que lee línea por línea las instrucciones del lenguaje de programación y las va ejecutando.
2. **Sin puntos y coma**, lo que reduce la cantidad de tiempo que uno a veces invierte buscando errores de sintáxis, como ocurre habitualmente en lenguajes como C++ y Java, entre otros.
3. Es de **tipado dinámico**, por lo que no necesitas definir cual es el tipo de una variable.
4. **Todo es un objeto**, lo que ofrece flexibilidad al lenguaje.
5. Es **muy productivo** ya que puedes terminar proyectos más rápidos que con otros lenguajes.
6. Puedes **reescribir el lenguaje**, es decir, puedes abrir una clase del lenguaje y agregar tus propios métodos (reescribir el lenguaje), tal como se detalló un poco más arriba.

### 2.3. ¿Quiénes usan Ruby?

1. Basecamp (principales promotores ya que ellos son los creadores del famoso Framework Ruby on Rails)
2. Github
3. Heroku
4. Tumblr
5. Airbnb
6. Twitter (originalmente)
7. Y un largo etc.

### 2.4. ¿Por qué utilizar Ruby?

* Si quieres **incrementar tu productividad**.
* Si te importa la **expresividad**.
* Si quieres un **lenguaje flexible**.
* Si no te gusta repetir código (**Don’t Repeat Yourself**, lo que en español significa **"No te repitas"**; es decir, escribir menos código y que el mantenimiento sea más práctico).
* Si quieres ser parte de una **comunidad activa** (Ruby tiene documentación, tutoriales y un largo etc. activos, además de poseer una de las mejores comunidades en lenguajes de programación).

## 3. Ruby on Rails

### 3.1. ¿Qué es?

Ruby on Rails (RoR) es un **Framework** de código abierto para desarrollar aplicaciones y servicios web utilizando **Ruby** como lenguaje de programación.

Este Framework fue desarrollado por David Heinemeier Hansson (DDH) como parte de su trabajo en Basecamp, y lanzado en julio de 2004.

Lo más probable es que te preguntes qué tiene de especial este Framework relativamente jóven y la respuesta es simple: grandes empresas y/o proyectos utilizan esta tecnología (Basecamp, Github, Airbnb, etc.) por lo que a pesar de tener un poco más de 15 años de vida, ha cambiado y evolucionado mucho en este corto periodo de tiempo.

### 3.2. Filosofía

La filosofía de Ruby on Rails se basa en 2 aspectos muy importantes:

#### 1. Don't Repeat Yourself (DRY)

Significa que **no deberíamos repetir código**, configuración o en otros casos hasta la documentación.

Un claro ejemplo sería que normalmente en una aplicación de Rails definimos la estructura (o configuración) de la base de datos en un solo lugar, y no en archivos externos y/o varios archivos como ocurre con otros Frameworks, logrando así ahorrar tiempo, trabajo y errores (ya que si queremos modificar algo solo debemos recurrir a dicho archivo y corregirlo).

#### 2. Convention over configuration

Significa que está construido sobre **convenciones en lugar de configuraciones**, es decir, hacer lo que nosotros podríamos pensar que hace.

Para que quede más claro lo que dije en el punto anterior, un ejemplo sería que Rails cuenta con ActiveRecord, el cual nos permite comunicarnos con la base de datos utilizando objetos en lugar de sentencias SQL, es decir, **¡Nada de SQL!**.

### 3.3. Arquitectura

Ruby on Rails hace uso de la arquitectura (o patrón) **MVC** (**Model View Controller**, que en español significa **Modelo Vista Controlador**), la cual simplifica la implementación de la aplicación dividiéndola en varias capas, donde cada una de ellas es responsable de realizar una tarea determinada.

MVC consta de 3 capas:

1. **Model**: se encarga de encapsular los datos y la lógica de negocios de la aplicación (tiene una constante comunicación con la base de datos).
2. **View**: nos ayuda a construir las vistas (o interfaces), las cuales estarán en constante interacción con el cliente.
3. **Controller**: se encarga de interpretar las entradas o peticiones de los clientes y también de responderlas (comunicándose ya sea con la capa Model o la capa View, dependiendo de lo que solicite el usuario).

La imagen que verás a continuación explica de una manera sencilla todo lo anteriormente explicado:

![MVC]({{ site.baseurl }}/assets/img/MVC.jpg)

### 3.4. Preguntas frecuentes

1. **¿Necesito saber Ruby?** Más que Ruby, HTML es esencial.
2. **¿Qué tengo que instalar?** Ruby, Ruby on Rails y Git.
3. **¿Qué voy a aprender?** Trabajar con bases de datos, vistas, configurar permisos y un largo etc.

### 3.5. ¡No olvidar!

Un **Framework** suele ser confundido con un **IDE**, lo cual es totalmente erróneo:

* **IDE**: Es solamente un editor de texto, posiblemente integrado con un compilador determinado, ofreciendo mayores facilidades para trabajar.
* **Framework**: Es un conjunto de utilidades para desarrollar aplicaciones, normalmente un conjunto de clases que facilitan el trabajo y las tareas más pesadas.

## 4. Git

Git es un **Sistema de Control de Versiones** diseñado por Linus Torvalds.

Por Control de Versiones me refiero a la gestión de los diversos cambios que se realizan sobre los elementos de algún producto o una configuración del mismo, es decir, es lo que hacemos al momento de desarrollar un software o una página web (subes tu código a la nube, le añades alguna parte o simplemente editas algo que no funciona correctamente, entre otros).

A partir de lo anterior, un Sistema de Control de Versiones serían todas las herramientas que nos permiten hacer esas modificaciones antes mencionadas sobre nuestro código y hacen que sea más fácil la administración de las distintas versiones, es decir, **Git**.
