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
hola(edad:27,nombre:"Nicolas")  # Hola joven Nicolas (no importa el orden)

# Utilizando el operador splat
def hola(nombre:"",edad:0,**options)  # Doble asterisco
  if edad > 30
    puts "Hola señor #{nombre}"
  else
    puts "Hola joven #{nombre}"
  end
  puts options
end

hola(edad:27,nombre:"Nicolas",color:"Azul",animal:"Perro")
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

hola(edad:27,nombre:"Nicolas",color:"Azul",animal:"Perro")  # ERROR
```

## 4. Clases

No olvidemos que en Ruby **todo es un objeto**, ya que es un lenguaje de programación totalmente **orientado a objetos** (POO por sus siglas en inglés). El comportamiento de los objetos es definido por una **clase**.

``` rb
class Video  # La primera letra debe ser mayúscula
  # Atributos
  attr_accessor :minutes, :tittle
  
  # Métodos
  def play
  end
  
  def pause
  end
  
  def stop
  end
end
```

Una clase se encarga de definir los **atributos**, **métodos**, **campos** y hasta los **eventos** que un objeto va a tener.

``` rb
class Video
  attr_accessor :minutes, :tittle
  
  def play
  end
  
  def pause
  end
  
  def stop
  end
end

# Inicializando un objeto de la clase Video
video_ruby_30 = Video.new  # También se dice que es una instancia de la clase
video_ruby_30.tittle = "Clases y objetos"

# Inicializamos otra clase
video_ruby_31 = Video.new
video_ruby_31.tittle = "Métodos y atributos"

puts video_ruby_30.tittle  # "Clases y objetos"
puts video_ruby_31.tittle  # "Métodos y atributos"
```

### 4.1. Constructor Initialize

Este constructor o método se ejecuta cuando creamos un objeto de una clase y se suele utilizar para inicializar valores que el objeto tendrá (algo así como un método por default).

``` rb
class Video
  attr_accessor :minutes, :tittle
  
  def initialize(tittle)
    self.tittle = tittle
  end
  
  def play
  end
  
  def pause
  end
  
  def stop
  end
end

video_ruby_30 = Video.new("Clases y objetos")  # Con new mandamos a llamar el método initialize
puts video_ruby_30.tittle  # "Clases y objetos"
```

### 4.2. Variables de instancia y métodos accesores

Las propiedades en una Clase se identifican por **variables de instancia**, es decir, identificadores que le pertenecen a un objeto y no a la clase (un objeto puede tener valores distintos en cada una de sus propiedades o variables).

``` rb
class Tutor
  def initialize(name)
    @nombre = name  # Variable de instancia (propiedad de un objeto)
  end
end

nicolas = Tutor.new("Nicolas")
franco = Tutor.new("Franco")
# Tenemos dos objetos que son instancia de la misma clase,
# Cada uno con un valor distinto para la propiedad @nombre

puts nicolas.nombre  # ERROR
puts franco.nombre  # ERROR
```

El error al tratar de imprimir por pantalla los nombres de los objetos creados radica en que las variables de instancia **no pueden ser modificadas u observadas desde fuera del objeto**, es decir, no podemos leerlas o acceder a su valor a menos que sea desde dentro del objeto (dentro de la descripción de la clase).

``` rb
class Tutor
  def initialize(name)
    @nombre = name
    puts @nombre
  end
end

nicolas = Tutor.new("Nicolas")
franco = Tutor.new("Franco")
# Nicolas
# Franco
```

La ventaja de estas variables es que podemos acceder a ellas desde cualquier parte del objeto, no importando si la declaramos dentro de un método y luego la leemos en otro.

``` rb
class Tutor
  def initialize(name)
    @nombre = name
  end
  
  def say_my_name
    puts @nombre
  end
end

nicolas = Tutor.new("Nicolas")
franco = Tutor.new("Franco")

nicolas.say_my_name  # "Nicolas"
franco.say_my_name  # "Franco"
```

Seguramente te estarás preguntando como podríamos entonces modificar y/o leer la(s) propiedad(es) de un objeto si las variables de instancia no lo permiten. Los **métodos accesores** solucionan este inconveniente ya que definen como podemos cambiar, asignar o modificar una propiedad y al mismo tiempo como leerla desde el objeto.

``` rb
class Tutor
  def initialize(name)
    @nombre = name
  end
  
  # Obtener una propiedad
  def get_nombre
    @nombre
  end
  
  # Asignar o modificar una propiedad
  def set_nombre(nombre)
    @nombre = nombre
  end
end

nicolas = Tutor.new("Nicolas")
franco = Tutor.new("Franco")

puts nicolas.get_nombre  # "Nicolas"

nicolas.set_nombre("Alex")
puts nicolas.get_nombre  # "Alex"
```

Los métodos accesores `getter` y `setter` también se pueden escribir de la siguiente manera:

``` rb
class Tutor
  def initialize(name)
    @nombre = name
  end
  
  def nombre  # Mismo nombre de la propiedad
    @nombre
  end
  
  def nombre=(nombre)  # Mismo nombre de la propiedad y el operador =
    @nombre = nombre
  end
end

nicolas = Tutor.new("Nicolas")
franco = Tutor.new("Franco")

# Método get
puts nicolas.nombre  # "Nicolas"

# Método set
nicolas.nombre = "Alex"
puts nicolas.nombre  # "Alex"
```

Ruby posee algunos métodos que nos permitirán de cierta manera **ahorrar** líneas de código:

``` rb
class Tutor
  attr_accessor :nombre  # Define los métodos get y set
  attr_reader :nombre  # Solo define el método get
  attr_writer :nombre  # Solo define el método set
end
```

## 5. Herencia

El concepto de **Herencia** hace referencia a crear una o más clases a partir de otra. En este proceso encontraremos dos conceptos claves:

1. Clase **Padre** o también llamada clase **Base**.
2. Clase **Hija** o **Subclase**, que viene siendo una clase basada en la **Clase Padre**.

``` rb
# Clase Padre
class Video
  attr_accessor :title, :duration
end

# Subclase
class YoutubeVideo < Video
  attr_accessor :youtube_id
end
# Esta clase hereda todas las propiedades y métodos de su padre

yt = YoutubeVideo.new
yt.title = "Herencia en Ruby"
yt.youtube_id = "asdf123"
puts yt.title  # "Herencia en Ruby"
puts yt.youtube_id  # "asdf123"
```

### 5.1. Sobrescribir métodos

Esta característica nos permite que una subclase o clase hija tenga una implementación específica (o algo distinta) de un método que ya nos proporciona su clase padre.

``` rb
class Video
  attr_accessor :title
  attr_accessor :duration
  attr_accessor :description
  
  def embed_video_code
    "<video></video>"
  end
  
  def setup(title)
    @title = title
  end
end

class FacebookVideo < Video
  attr_accessor :facebook_id
end

class YoutubeVideo < Video
  attr_accessor :youtube_id
  
  def embed_video_code
    "<iframe />"
  end
end

puts FacebookVideo.new().embed_video_code  # "<video></video>"
puts YoutubeVideo.new().embed_video_code  # "<iframe />"
```

Esta implementación **anula** (o reemplaza) al método de la superclase.

### 5.2. `super`

Si quisiéramos sobrescribir un método en una subclase **sin perder** lo que el padre hace, utilizamos la palabra reservada `super`.

``` rb
class Video
  attr_accessor :title
  attr_accessor :duration
  attr_accessor :description
  
  def embed_video_code
    "<video></video>"
  end
  
  def setup(title)
    @title = title
  end
end

class YoutubeVideo < Video
  attr_accessor :youtube_id
  
  def embed_video_code
    "<iframe />"
  end
  
  def setup(title)
    super  # Llama al método del mismo nombre en la clase padre
    # Podemos agregar más funcionalidades si así lo queremos
  end
end

yt = YoutubeVideo.new
yt.setup("Herencia en Ruby")
puts yt.title  # "Herencia en Ruby"
```

### 5.3. Clase Object

En Ruby, todas las clases heredan de la **Clase Object**, la cual vendría siendo una especie de **Super Clase** o **Primera Clase**. Esto significa que todos los métodos y propiedades definidas en esta clase estarán disponibles en todos los objetos que hay en el lenguaje.

``` rb
class Video
  attr_accessor :title
  attr_accessor :duration
  attr_accessor :description
  
  def embed_video_code
    "<video></video>"
  end
  
  def setup(title)
    @title = title
  end
end

class YoutubeVideo < Video
  attr_accessor :youtube_id
  
  def embed_video_code
    "<iframe />"
  end
  
  def setup(title)
    super
  end
end

puts YoutubeVideo.new.object_id  # 46267240

puts 1.object_id  # 3
```

Con esta clase podríamos, por ejemplo, crear propiedades o métodos para todos los objetos de un programa:

``` rb
class Object
  def i_have_superpowers
    puts "Soy Dios"
  end
end

class Video
  attr_accessor :title
  attr_accessor :duration
  attr_accessor :description
end

[].i_have_superpowers  # "Soy Dios"
1.i_have_superpowers  # "Soy Dios"
"Hola".i_have_superpowers  # "Soy Dios"
Video.new.i_have_superpowers  # "Soy Dios"
```

### 5.4. Alcance de los métodos

Los métodos de un objeto en Ruby se pueden clasificar en:

1. Públicos (`public`): Se pueden mandar a llamar desde cualquier lugar (por defecto todos los métodos que uno crea son públicos).
2. Privados (`private`): Se pueden llamar únicamente desde dentro de la clase. Una diferencia de otros lenguajes, en Ruby una clase hija **si hereda** los métodos privados de su padre.
3. Protegidos (`protected`): Se pueden llamar desde otras clases siempre y cuando sean del mismo tipo.

El alcance de una variable o método hace referencia a desde donde puedo mandarlo a llamar.

``` rb
class Humano
  def initialize
    self.publico
  end
  
  def publico
    puts "Soy público"
  end
  
  private
  # Todos los métodos que agreguemos por debajo de esta palabra serán privados
    def privado
      puts "Soy privado"
    end
  
  protected
  # Todos los métodos que agreguemos por debajo de esta palabra serán protegidos
    def protegido
      puts "Soy protegido"
    end
end

clas Tutor < Humano
  def initialize
    @inner = Humano.new
  end
  
  def llamar_protegido
    @inner.protegido
  end
end

class Alien
  def initialize
    @inner = Humano.new
  end
  
  def llamar_protegido
    @inner.protegido
  end
end

Humano.new  # "Soy público"
Humano.new.privado  # ERROR

tutor = Tutor.new
alien = Alien.new

puts tutor.is_a?(Humano)  # TRUE (podemos llamar al método protegido)
puts alien.is_a?(Humano)  # FALSE
```

### 5.5. Métodos de clase

Uno de los secretos de Ruby es que **las clases también son ojetos**. Veamos un ejemplo:

``` rb
class SoyObjetoLoJuro
  # Variable de instancia
  @nombre_clase = "Soy objeto lo juro"
  
  # Método de clase (o estático)
  def self.nombre_clase
    @nombre_clase
  end
end
```

La particularidad de los métodos de clase es que se mandan a llamar sobre la clase y no sobre una instancia o un objeto de dicha clase.

``` rb
class SoyObjetoLoJuro
  @nombre_clase = "Soy objeto lo juro"
  
  def self.nombre_clase
    @nombre_clase
  end
  
  def self.nombre_clase=(nombre_clase)
    @nombre_clase = nombre_clase
  end
end

puts SoyObjetoLoJuro.nombre_clase  # "Soy objeto lo juro"

SoyObjetoLoJuro.nombre_clase = "Otra cosa"
puts SoyObjetoLoJuro.nombre_clase  # "Otra cosa"
```

Los métodos de clase anteriores también se pueden escribir de la siguiente manera:

``` rb
class SoyObjetoLoJuro
  @nombre_clase = "Soy objeto lo juro"
  
  class << self
  
    def nombre_clase
      @nombre_clase
    end
  
    def nombre_clase=(nombre_clase)
      @nombre_clase = nombre_clase
    end
  
  end
end
```

### 5.6. Variables de clase

Al igual qué los métodos tenemos las variables de clase, las cuales se identifican por el doble `@`:

``` rb
class Video
  @@type = "video/mp4"
  
  # Método de clase
  def self.type_desde_clase
    puts @@type
  end
  
  # Método a nivel del objeto
  def type_desde_objeto
    puts @@type
  end
end

Video.type_desde_clase  # "video/mp4"
Video.new.type_desde_objeto  # "video/mp4"
```

Su principal característica es que se pueden utilizar desde un método de la clase o un método del objeto.

Una segunda característica de estas variables es su comportamiento cuando hay Herencia:

``` rb
class Video
  @@de_clase = "Clase woo"
  @de_instancia = "Instancia yeei"
end

class Youtube < Video
  def self.test
    puts @@de_clase
    puts @de_instancia
  end
end

Youtube.test
# "Clase woo" (la variable de clase se herada)
# nil (la variable de instancia solo le pertenece a Video)
```

Una cosa importante a considerar es que si modificamos la variable de clase, ya sea en el padre o en una de sus clases hijas, dichos cambios se verán reflejados en todas las clases (ya que guardan la misma referencia).

``` rb
class Video
  @@de_clase = "Clase woo"
  @de_instancia = "Instancia yeei"
  
  def self.test
    puts @@de_clase
    puts @de_instancia
  end
end

class Youtube < Video
  def self.test
    @@de_clase = "Clase cambiada"
    puts @@de_clase
    puts @de_instancia
  end
end

Youtube.test
# "Clase cambiada"
# nil
Video.test
# "Clase cambiada"
# "Instancia yeei"
```

A partir del ejemplo anterior, lo más probable es que te estés preguntando cuándo utilizar variables de instancia y cuándo variables de clase:

* Las **variables de instancia** conviene utilizarlas si no queremos que se hereden a las clases hijas (únicamente le pertenecerá a esa clase).
* Si queremos tener el beneficio de la herencia y acceder desde métodos del objeto o métodos de la clase, es conveniente utilizar **variables de clase**.

## 6. Polimorfismo

Hola amigos.

## X. Bibliografía

1. [Ruby](https://www.ruby-lang.org/es/documentation/quickstart/) en 20 minutos.
2. [CódigoFacilito](https://codigofacilito.com/articulos/por-que-aprender-ruby), curso gratuito de Ruby.
3. [Udemy](https://www.udemy.com/course/curso-ruby-rails/), curso pagado de Ruby y Ruby on Rails.
4. [Ruby Guides](https://www.rubyguides.com/ruby-tutorial/), tutorial gratuito para principiantes (en inglés).

|     |     |
|:----|----:|
| [< Lección N°4](https://nisoto.github.io/rails-iv-ruby-basico/){: .btn .btn-info} | [Lección N°6 >](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} |
