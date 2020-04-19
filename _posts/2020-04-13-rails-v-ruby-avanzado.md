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

La ventaja de un Hash es que podemos acceder a su información de manera más rápida por medio de su clave:

``` rb
tutor = { "nombre" => "Nicolas", "edad" => 27, 20 => "Numero", [] => "Arreglo" }
tutor_dos = { :nombre => "Nicolas", :edad => 27, :cursos => 10 }
puts tutor["nombre"]  # "Nicolas"
puts tutor[[]]  # "Arreglo"
puts tutor_dos[:nombre]  # "Nicolas"
```

Al igual que los arreglos, agregar elementos es bastante sencillo:

``` rb
tutor = { "nombre" => "Nicolas", "edad" => 27, 20 => "Numero", [] => "Arreglo" }
tutor["cursos"] = 10
puts tutor["cursos"]  # 10
```

En caso de que intentáramos acceder a un Hash con una clave inexistente (no válida) Ruby nos retornará nulo (nil):

``` rb
tutor = { "nombre" => "Nicolas", "edad" => 27, 20 => "Numero", [] => "Arreglo" }
puts tutor[5]  # nil

# Podemos agregar un mensaje por default si accedemos a una clave no válida
tutor.default = "No existe esa clave"
puts tutor[5]  # "No existe esa clave"
```

El método `each` también nos será útil si queremos recorrer un Hash:

``` rb
tutor = { :nombre => "Nicolas", :edad => 27, :cursos => 10 }
tutor.each do |clave,valor|  # Recibe 2 parámetros
  puts "En #{clave} tenemos #{valor}"
end
# En nombre tenemos Nicolas
# En edad tenemos 27
# En cursos tenemos 10
```

## X. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°4](https://nisoto.github.io/rails-iv-ruby-basico/){: .btn .btn-info} | [Lección N°6 >](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} |
