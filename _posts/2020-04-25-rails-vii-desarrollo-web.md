---
layout: post
title: "Ruby on Rails VII: Desarrollo Web"
date: 2020-04-25
excerpt: "Capítulo N°7 del curso de Ruby on Rails"
tags: [rails]
---

## 1. Conceptos previos

1. **World Wide Web (WWW)**: Se le llama al sistema de documentos de hipertexto que se encuentran enlazados entre sí y a los que se accede por medio de Internet. A través de un software conocido como navegador, los usuarios pueden visualizar diversos sitios web (los cuales contienen texto, imágenes, videos y otros contenidos multimedia) y navegar a través de ellos mediante los hipervínculos.
2. **Internet**: Es una red de redes que permite la interconexión descentralizada de computadoras a través de un conjunto de protocolos denominado TCP/IP.
3. **Intranet**: Es una red informática que utiliza la tecnología del protocolo de Internet para compartir información, sistemas operativos o servicios de computación dentro de una organización. Suele ser interna (a diferencia del Internet que es público), por lo que solo los miembros de esa organización tienen acceso a ella.
4. **Hipertexto**: Es una estructura no secuencial que nos permite crear, agregar, enlazar y compartir información de diversas fuentes por medio de enlaces asociativos y redes sociales. Es básicamente texto que contiene enlaces a otros textos.
5. **Hipervínculo**: También conocido como hiperenlace, enlace o vínculo, es un elemento de un documento electrónico que hace referencia a otro recurso, como por ejemplo un punto específico de un documento o de otro documento.
6. **Página web**: Es un documento digital de carácter multimediático (es decir, capaz de incluir audio, video, texto y sus combinaciones), adaptado a los estándares de la World Wide Web (WWW) y a la que se puede acceder a través de un navegador web y una conexión activa a Internet.
7. **Navegador web**: Es un programa que permite ver la información que contiene una página web. El navegador interpreta el código (HTML generalmente), en el que está escrita la página web y lo presenta en pantalla permitiendo al usuario interactuar con su contenido y navegar por ella.
8. **HTML**: Cuyas siglas significan HyperText Markup Language (Lenguaje de Marcas de Hipertexto), es el lenguaje con el que se define el contenido de las páginas web. Básicamente se trata de un conjunto de etiquetas que sirven para definir el texto y otros elementos que compondrán una página web, como imágenes, listas, videos, etc.
9. **Protocolo**: Son instrucciones, normativas o reglas que permiten guiar una acción o que establecen ciertas bases para el desarrollo de un procedimiento.
10. **Protocolo de comunicación**: Se trata del conjunto de pautas que posibilitan que distintos elementos que forman parte de un sistema establezcan comunicaciones entre sí, intercambiando información. Si nos centramos en las computadoras, el protocolo de comunicación determina cómo deben circular los mensajes dentro de una red. Cuando la circulación de la información se desarrolla en Internet, existen una serie de protocolos específicos que posibilitan el intercambio. Los protocolos de comunicación en Internet más importantes son TCP e IP, ya que su acción conjunta (TCP/IP) posibilita el enlace entre todos los equipos que acceden a la red.
11. **Protocolo TCP**: Cuyas siglas significan Protocolo de Control de Transmisión, se utiliza para crear conexiones entre sí a través de las cuales puede enviarse un flujo de datos. Este protocolo garantiza que los datos serán entregados en su destino sin errores y en el mismo orden en que se transmitieron.
12. **Protocolo IP**: Cuyas siglas significan Protocolo de Internet, su principal función consiste en permitir la comunicación en dos direcciones (destino y origen), para que sea posible la transmisión de datos a través de un protocolo no orientado a conexión que envía paquetes conmutados por medio de diferentes redes físicas que han sido enlazadas con anterioridad siguiendo la norma OSI.
13. **Protocolo no orientado a conexión**: Significa una comunicación entre dos puntos finales de una red en los que un mensaje puede ser enviado desde un punto final a otro sin acuerdo previo.
14. **Paquete conmutado**: Es un método de agrupar los datos transmitidos a través de una red digital en paquetes que se componen de un encabezado y una carga útil.
15. **Norma OSI**: sus siglas significan Open System Interconnection (Sistema de Interconexión Abierto), aunque también se le conoce como Modelo de Interconexión de Sistemas Abiertos. Este modelo sirve como referencia para los protocolos de la red y es un estándar que tiene por objetivo conseguir interconectar sistemas de procedencia distinta para que estos puedan intercambiar información sin ningún tipo de impedimentos.
16. **Desarrollo web**: Es un término que define la **creación** de sitios web para Internet o una Intranet. Para conseguirlo, hace uso de tecnologías de software del lado del servidor y del cliente que involucran una combinación de procesos de **base de datos** con el uso de un **navegador web** con el propósito de realizar determinadas tareas o mostrar información.
17. **Servidor**: Corresponde a un ordenador u otro tipo de dispositivo que suministra información requerida por un cliente. Algunos tipos de servidores son los de Correo, Proxy, Web y de Base de Datos, entre otros.
18. **Servidor web**: Es el encargado de manejar páginas web y enviarlas a través de la red a quienes lo requieran y tengan los permisos para dichas páginas. Son los principales encargados de generar el tráfico en Internet puesto que a través de ellos se realizan las conexiones a todos los sitios web del mundo.

Importante:
* **Internet** es una inmensa red de computadoras alrededor de todo el mundo conectadas entre sí, mientras que la **Web** (World Wide Web) es una enorme colección de páginas que se asienta sobre esa red de computadoras. Por lo tanto, cuando navegamos a través de nuestro celular o computadora usamos Internet para acceder a la Web.

## 2. Modelo Cliente-Servidor

La expresión **cliente servidor** se utiliza en el ámbito de la informática, en donde el **cliente** corresponde al dispositivo que requiere ciertos servicios a un servidor, mientras que el **servidor** por su parte, alude al equipo que brinda servicios a las computadoras (ordenadores) que se hallan conectadas con él mediante una red.

Por lo tanto, este concepto corresponde a un modelo de comunicación que vincula a varios dispositivos informáticos a través de una red. El cliente en este marco, realiza peticiones de servicios al servidor, el cual se encarga de satisfacer dichos requerimientos.

![ModeloClienteServidor]({{ site.baseurl }}/assets/img/ModeloClienteServidor.jpg)

Con esta arquitectura, las tareas se distribuyen entre los servidores (que proveen los servicios) y los clientes (que demandan dichos servicios). Dicho de otro modo, el cliente le pide un recurso al servidor, que brinda una respuesta.

Este tipo de modelos permite repartir la capacidad de procesamiento ya que el servidor puede ejecutarse sobre más de un equipo y ser más de un programa. De acuerdo a los servicios que brinda, se lo puede llamar servidor web, servidor de correo o de otro modo.

Elementos de este modelo:

#### 1. HTTP

Cuyas siglas significan Hypertext Transfer Protocol (Protocolo de transferencia de hipertexto), es un protocolo de comunicación que permite las transferencias de información en la World Wide Web, utilizando para ello el modelo Cliente-Servidor.

#### 2. Mensajes

Los mensajes en este modelo son en texto plano, convirtiéndolo así en algo más legible y fácil de depurar.

Estructura:
* Petición: Método de petición + URL del recurso + Versión HTTP.
* Respuesta: Versión HTTP + Código de respuesta + Frase asociada al retorno.

#### 3. URI

Son las siglas de Uniform Resource Identifier (Identificador Uniforme de Recursos) y sirve para identificar recursos en Internet, el cual tiene un formato estándar definido y su propósito es permitir interacción entre recursos disponibles en Internet, o en alguna red de cómputo. Los recursos a los que se refiere son páginas, servicios, imágenes, videos, etc.

Algunos ejemplos:
* http://joyas.com/anillos/5
* http://joyas.com/aros
* http://joyas.com/aros/6/verdes

#### 4. URL

Son las siglas de Uniform Resource Locator (Localizador de Recursos Uniforme) y es un Identificador de Recursos Uniforme (URI) cuyos recursos referidos pueden cambiar, esto es, la dirección puede apuntar a recursos variables en el tiempo. Están formados por una secuencia de caracteres de acuerdo con un formato y estándar que designa recursos en una red como por ejemplo el Internet.

#### 5. URN

Son las siglas de Uniform Resource Name (Nombre de Recurso Uniforme) e identifican recursos en la web, pero a diferencia de los URL, no indican exactamente dónde se encuentra ese objeto.

Básicamente, un URI está constituido por un URL más un URN o bien, por solo uno de ellos:

**URI = URL y/o URN**

## 3. Métodos de petición

Para realizar solicitudes a un servidor por medio del protocolo HTTP, es obligatorio el uso de métodos que vienen predefinidos en este protocolo, los cuales le indican al servidor cuál es la acción que se desea realizar sobre uno o varios recursos en concreto. A estos métodos también se les conoce por el nombre de **verbos**.

Dichos métodos son los siguientes:

1. **GET**: Solicita una representación de un recurso específico. Las peticiones que usan este método sólo deben recuperar datos (por ejemplo, `GET /images/logo.png`).
2. **HEAD**: Pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.
3. **POST**: Se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
4. **PUT**: Reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
5. **DELETE**: Borra un recurso en específico.
6. **CONNECT**: Establece un túnel hacia el servidor identificado por el recurso.
7. **OPTIONS**: Es utilizado para describir las opciones de comunicación para el recurso de destino.
8. **TRACE**: Realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.
9. **PATCH**: Es utilizado para aplicar modificaciones parciales a un recurso.

En resumen, los principales métodos a utilizar son los siguientes:
* **PUT** que sirve para **crear**.
* **GET** que sirve para **leer**.
* **POST** que sirve para **actualizar**.
* **DELETE** que sirve para **borrar**.

## 4. Modelo Vista Controlador (MVC)

El **Modelo Vista Controlador** o **MVC** (abreviado) es un **patrón de arquitectura** de software que separa los datos de una aplicación, la interfaz de usuario y la lógica de control en 3 componentes distintos.

Es una arquitectura muy importante ya que se utiliza tanto en componentes gráficos básicos como sistenas empresariales. La mayoría de los Frameworks modernos utilizan MVC (o alguna adaptación) para la arquitectura, donde podemos destacar **Ruby on Rails**, **Django** y **AngularJS**, entre otros.

![MVC2]({{ site.baseurl }}/assets/img/MVC2.jpg)

Una analogía que nos ayuda bastante a entender este patrón es la televisión. En nuestra televisión podemos ver distintos canales distribuidos por un proveedor (**Modelo**), todos los canales que podemos ver son la **Vista**, y nosotros cambiando de canal, controlando qué ver representamos al **Controlador**.

En la web, el MVC funciona de la siguiente manera:

* El usuario manda una petición al navegador: ver un curso de Ruby.
* El controlador responde a la solicitud ya que él es quien controla la lógica de la aplicación y le pide al modelo la información del curso.
* El modelo, que se encarga de los datos de la aplicación, consulta la base de datos y le responde al controlador con los datos que pidió.
* Una vez que el controlador tiene los datos del curso de Ruby, se los envía a la vista, quien se encarga de aplicar los estilos, organizar la información y construir la página que vemos en el navegador.

Resumamos entonces los conceptos:

1. **Modelo**: Se encarga de los datos generalmente (pero no obligatoriamente) consultando la base de datos. Aquí podemos encontrar tareas como actualizaciones, consultas, búsquedas y un largo etc.
2. **Vistas**: Son la representación visual de los datos, todo lo que tenga que ver con la interfaz gráfica va aquí. Ni el modelo ni el controlador se preocupan de cómo se verán los datos, esa responsabilidad es únicamente de la vista.
3. **Controlador**: Recibe las órdenes del usuario y se encarga de solicitar los datos al modelo y de comunicárselos a la vista.

|     |     |
|:----|----:|
| [< Lección N°6](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} | [Lección N°8 >](https://nisoto.github.io/rails-viii-ruby-on-rails/){: .btn .btn-info} |
