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

### 1.1. Iterando un Hash

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

### 1.2. Operaciones con Hashes

Existen varios métodos que nos permiten trabajar los Hashes, algunos de ellos son:

``` rb
tutor = { :nombre => "Nicolas", :edad => 27, :cursos => 10 }

# Determina la cantidad de elementos que tiene el Hash
puts tutor.length  # 3
puts tutor.size  # 3

# Determina si una clave existe dentro del Hash
puts tutor.has_key?(:nombre)  # TRUE
puts tutor.has_key?(:asdasd)  # FALSE

# Determina si un valor existe dentro del Hash
puts tutor.has_value?("Nicolas")  # TRUE
puts tutor.has_value?(27)  # TRUE
puts tutor.has_value?("Hola Mundo")  # FALSE

# Retorna un arreglo con las claves del Hash
puts tutor.keys  # nombre, edad, cursos

# Retorna un arreglo con los valores del Hash
puts tutor.values  # Nicolas, 27, 10

# Elimina todos los elementos del Hash
tutor.clear
puts tutor  # {}

# Elimina un valor del Hash por medio de su clave
tutor.delete(:cursos)
puts tutor  # {:nombre => "Nicolas", :edad => 27}

# Determina si el Hash está vacio
puts tutor.empty?  # FALSE
tutor.clear
puts tutor.empty?  # TRUE

# Retorna la clave del Hash a partir de un valor
puts tutor.key("Nicolas")  # nombre

# Invierte el orden del Hash (claves por valor y vice versa)
puts tutor.invert  # {"Nicolas" => :nombre, 27 => :edad, 10 => :cursos}

# Combinar dos Hashes
user_info = { :apellido => "Soto", :estado => 1 }
puts tutor.merge(user_info)  # {:nombre => "Nicolas", :edad => 27, :cursos => 10, :apellido => "Soto", :estado => 1}
```

## 2. Símbolos

Los símbolos corresponden a **cadenas inmutables** que no pueden ser modificadas en tiempo de ejecución.

``` rb
cadena1 = "nicolas"
cadena1.capitalize!
puts cadena1  # Nicolas

cadena2 = :nicolas
cadena2.capitalize!
puts cadena2  # ¡ERROR!
```

Algo importante a considerar es que si tenemos dos símbolos cuyo valor sea el mismo y se encuentren en distintas variables, compartirán el **mismo `object_id`**:

``` rb
cadena1 = "Nicolas"
cadena2 = "Nicolas"
simbolo1 = :Nicolas
simbolo2 = :Nicolas
puts cadena1.object_id  # 42748280
puts cadena2.object_id  # 45992400
puts simbolo1.object_id  # 1998628
puts simbolo2.object_id  # 1998628
```

Seguramente te estarás preguntando cuándo conviene utilizar símbolos y para ello tenemos algunas restricciones:

1. Cuando no necesitamos modificar el `string`.
2. Cuando no necesitamos los métodos del `string`
3. Son bastante útiles para ser usados como nombres (como clave en un Hash, por ejemplo).

## 3. Métodos

Un método no es nada más que una forma de manipular un objeto.

``` rb
def square(x)
  # Retorna el cuadrado de un numero
  return 0 unless x.is_a? Integer
  return x * x
end
=begin
La palabra reservada return se puede ignorar,
en ese caso el método retornará la última línea
=end

def saludar
  puts "Hola Nicolas"
end

puts square(2)  # 4
puts square(3)  # 9
puts square("3")  # 0

saludar()  # "Hola Nicolas"
```

### 3.1. Operador `splat`

Este operador nos será de gran utilidad si queremos definir una cantidad variable de parámetros a un método. Veamos el ejemplo a continuación:

``` rb
# Método que recibe un arreglo de personas y las saluda
def hola_gente(personas)
  personas.each {|persona| puts "Hola #{persona}"}
end

hola_gente(["Nicolas","Franco","Fabian"])
# Hola Nicolas
# Hola Franco
# Hola Fabian
hola_gente("Nicolas")  # ERROR
hola_gente(23)  # ERROR

# Los inconvenientes anteriores se solucionan con el operador splat
def hola_gente(*personas)
  personas.each {|persona| puts "Hola #{persona}"}
end

hola_gente "Nicolas", "Franco"
# Hola Nicolas
# Hola Franco

hola_gente 23
# Hola 23

# Con este operador podemos pasar varios argumentos y él los recibirá como un arreglo

nombres = ["Nicolas", "Franco", "Fabian"]
hola_gente nombres
# Hola ["Nicolas", "Franco", "Fabian"]
hola_gente *nombres  # El asterisco convierte el array a una lista de parámetros
# Hola Nicolas
# Hola Franco
# Hola Fabian
```

### 3.2. Keyword arguments

Los **keyword arguments** son una forma de asignar valores por default a los parámetros de un método.

``` rb
def hola(nombre:"",edad:0)
  if edad > 30
    puts "Hola señor #{nombre}"
  else
    puts "Hola joven #{nombre}"
  end
end

hola(nombre:"Nicolas",edad:27)  # Hola joven Nicolas
hola(nombre:"Nicolas",edad:35)  # Hola señor Nicolas
hola(nombre:"Nicolas")  # Hola joven Nicolas (edad por default es 0)
hola()  # Hola joven
hola(edad:27,nombre:"Nicolas)  # Hola joven Nicolas (no importa el orden)

# Utilizando el operador splat
def hola(nombre:"",edad:0,**options)  # Doble asterisco
  if edad > 30
    puts "Hola señor #{nombre}"
  else
    puts "Hola joven #{nombre}"
  end
  puts options
end

hola(edad:27,nombre:"Nicolas,color:"Azul",animal:"Perro")
# Hola joven Nicolas
# {:color => "Azul", :animal => "Perro"}
# Las opciones adicionales son recibidas en un Hash
```

Así como podemos asignar valores por defecto, también podemos decidir si alguno de los parámetros de un método debe ser obligatorio:

``` rb
def hola(nombre:"",edad:0,apellido:,**options)  # El parámetro apellido es obligatorio
  if edad > 30
    puts "Hola señor #{nombre}"
  else
    puts "Hola joven #{nombre}"
  end
  puts options
end

hola(edad:27,nombre:"Nicolas,color:"Azul",animal:"Perro")  # ERROR
```

## 4. Clases

Pendiente.

## X. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°4](https://nisoto.github.io/rails-iv-ruby-basico/){: .btn .btn-info} | [Lección N°6 >](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} |
