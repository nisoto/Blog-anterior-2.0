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

1. **GET**: Este método se utiliza cuando se necesita adquirir un archivo o recurso que se encuentran en un servidor web. Devuelve tanto las cabeceras que contienen los metadatos del recurso solicitado como el recurso en si (por ejemplo, `GET /images/logo.png`).
2. **HEAD**: Este método realiza una acción similar al método GET solo que a diferencia de este, solicita los metadatos de un recurso o archivo y no todo elemento como tal.
3. **POST**: Este método se usa cuando se necesita enviar información o un elemento al servidor y que lo enviado sea almacenado como un "hijo" o subelemento de un elemento o recurso ya existente en el servidor. Este método se usa para enviar información a un recurso web del servidor  mas no para cargar/crear un elemento nuevo como tal. Se usa principalmente en el envío de formularios que se encuentran en las páginas web.
4. **OPTIONS**: Sirve para averiguar que métodos HTTP soporta el servidor web con respecto a un recurso en concreto o en caso de que haya un * en la URI se devuelven todos los métodos soportados por el servidor.
5. **PUT**: Crea o carga un nuevo recurso al servidor, o en caso de que el objeto ya exista reemplaza el recurso existente con el recurso que se carga.
6. **DELETE**: Este método le solicita al servidor web que se borre un recurso en específico.
7. **TRACE**: Este método permite monitorear los mensajes que hay entre el cliente y el servidor web. Principalmente se usa con propósitos de diagnósticos de fallas o para revisar si existen servidores intermediarios en la conexión.
8. **CONNECT**: Este método se utiliza para solicitar una conexión de tipo túnel TCP/IP. Principalmente se utiliza cuando se necesita utilizar un proxy para una conexión segura cifrada HTTPS o para comunicaciones vía SSL.

En resumen, los principales métodos a utilizar son los siguientes:
* **PUT** que sirve para **crear**.
* **GET** que sirve para **leer**.
* **POST** que sirve para **actualizar**.
* **DELETE** que sirve para **borrar**.

|     |     |
|:----|----:|
| [< Lección N°6](https://nisoto.github.io/rails-vi-git-en-detalle/){: .btn .btn-info} | [Lección N°8 >](https://nisoto.github.io/rails-viii-ruby-on-rails/){: .btn .btn-info} |
