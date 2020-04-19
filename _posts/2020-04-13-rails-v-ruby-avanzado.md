---
layout: post
title: "Ruby on Rails V: Ruby avanzado"
date: 2020-04-13
excerpt: "Capítulo N°5 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Hashes

También conocidos como **arreglos asociativos** o **diccionarios**, su principal diferencia radica en cómo podemos acceder a los elementos que almacena. Es decir, mientras en los arreglos normales accedemos a sus elementos por medio de un **índice**, en un **Hash** lo hacemos a través de una **clave** (que puede ser cualquier tipo de objeto).

``` rb
tutor = { "nombre" => "Nicolas", "edad" => 27, 20 => "Numero", [] => "Arreglo" }
tutor_dos = { :nombre => "Nicolas", :edad => 27, :cursos => 10 }  # Hash con simbolos (recomendado)
tutor_tres = { nombre: "Nicolas", edad: 27, cursos: 10 }
puts tutor  # {"nombre" => "Nicolas", "edad" => 27, 20 => "Numero", [] => "Arreglo"}
puts tutor_dos  # {:nombre => "Nicolas", :edad => 27, :cursos => 10}
puts tutor_tres  # {:nombre => "Nicolas", :edad => 27, :cursos => 10}
```

|     |     |
|:----|----:|
| [< Lección N°4](https://nisoto.github.io/rails-iv-ruby-basico/){: .btn .btn-info} | [Lección N°6 >](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} |
