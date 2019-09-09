---
id: 2745
title: Arquitectura de microservicios para el desarrollo de software
date: 2019-07-22T11:15:15-03:00
author: Macarena MIllapán
excerpt: muy popular se ha vuelto este nuevo enfoque en el desarrollo de aplicaciones, pero ¿de qué se trata? y ¿Qué involucra? esto y otras cosas te los contaré en el post de esta semana.
layout: revision
guid: https://consultancysoft.com/2742-revision-v1/
permalink: /2742-revision-v1/
---
muy popular se ha vuelto este nuevo enfoque en el desarrollo de aplicaciones, pero ¿de qué se trata? y ¿Qué involucra? esto y otras cosas te los contaré en el post de esta semana.

## Una arquitectura que evoluciona

Esta arquitectura está basada en una anterior llamada arquitectura orientada a servicios o Service-oriented architecture de inglés, y como su nombre lo indica esta busca desarrollar los componentes del software como servicios que se comunican entre ellos, un servicio correspondería a una representación lógica de una actividad de negocio que tiene un resultado de negocio específico. Esta orientación de desarrollo de software no es una idea nueva, fue descrito por Gartner en 1996.

## ¿Qué son entonces los microservicios?

este es un enfoque para la construcción de sistemas de software con la que cada una de las funcionalidades de las capas de un sistema se divide en módulos que realizan una única funcionalidad, de esta forma tenemos distintas piezas que se ensamblan y, juntas, realizan las operaciones requeridas en su construcción. Cada microservicio puede estar construido en lenguajes diferentes, no es necesario que se encuentren en el mismo, es posible tener operaciones en java, otras en C++ o C#, una interfaz gráfica hecha con JavaScript, etc. Y estos microservicios deben comunicarse entre sí a través de solicitudes HTTP.

Los microservicios suelen hacer uso de las bases de datos no relacionales, estas ayudan a la creación de microservicios más rápidos y efectivos, entre estas podemos encontrar a MongoDB un sistema popular en este tipo de desarrollos.

Básicamente un microservicio requiere de por lo menos tres componentes principales, un elemento que cree nuevos objetos del tipo requerido para el microservicio, un controlador y otro elemento que se comunique con los datos.

## ¿Cuáles son los pro y los contras de la arquitectura de microservicios?

Como ventajas podríamos nombrar las siguientes.

  * Al dividir las componentes en pequeñas piezas funcionales podríamos hacer mejor uso de los recursos humanos disponibles, ya que cada pequeño grupo o individuo podría estar trabajando en paralelo para la construcción de un elemento.
  * Permite sistemas más escalables en el tiempo.
  * Permite la identificación de errores más rápido que revisando un largo código.
  * Permite la reparación de errores sin comprometer el funcionamiento integran de todo el sistema.
  * Cada microservicio requiere menos tiempo de desarrollo.

Desventajas

En cuanto a los contras de la implementación de estos sistemas

  * La poca claridad de cuando se requiere un microservicio y cuando se pueden llegar a unir funcionalidades.
  * Es necesario realizar un esfuerzo extra diseñando la comunicación de los microservicios.<figure class="wp-block-image">

<img src="https://consultancysoft.com/wp-content/uploads/2019/07/markus-spiske-70Rir5vB96U-unsplash-1024x683.jpg" alt="" class="wp-image-2743" srcset="https://consultancysoft.com/wp-content/uploads/2019/07/markus-spiske-70Rir5vB96U-unsplash-1024x683.jpg 1024w, https://consultancysoft.com/wp-content/uploads/2019/07/markus-spiske-70Rir5vB96U-unsplash-300x200.jpg 300w, https://consultancysoft.com/wp-content/uploads/2019/07/markus-spiske-70Rir5vB96U-unsplash-768x512.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /> </figure> 

## Una nueva visión

Ahora bien, los microservicios se basan en una idea similar a la arquitectura SOA, aunque se diferencian fundamentalmente en que los microservicios son más escalables que la arquitectura basada en servicios cuando se trabaja en la nube, aquí se encuentran distintos componentes que realizan una única función en el desarrollo de un sistema de software, no se tiene claro ni hay una guía para definir cuando un requerimiento es lo suficientemente grande o pequeño para poder catalogarse como un microservicio, pero siempre es bueno tener las siguientes recomendaciones:

1. ¿El proceso que estoy desarrollando podría ser utilizado por otro componente en el futuro? por ejemplo, un sistema que necesita almacenar personas y, posteriormente el validar los CI de cada uno de los elementos Persona almacenado en una base de datos, esta validación podría usarse no solo para almacenar, sino que posteriormente se podría necesitar para algún nuevo componente

2. ¿El proceso se conecta con una base de datos? Es necesario realizar microservicios cuya única función sea el ingreso y consulta de elementos almacenados en bases de datos, esto debido a que si más microservicios tienen acceso a la escritura y lectura de los registros en una base de datos podría ocasionar un gran conflicto con la integridad de los mismos.

3. ¿Cuáles son en definitiva los procesos que debo realizar? esto se relaciona a cuando se que estoy haciendo trabajo demás, una de las cosas que también puede pasar cuando se está realizando un desarrollo de software, y que siempre hay que tener en cuenta es cuando se está haciendo trabajo demás, no siempre es necesario que mi microservicio almacene la información que está generando y que debamos crear otro para almacenar en una nueva base de datos, muchas veces esta componente que nos adelantamos a realizar la puede estar desarrollando oro equipo y hasta en otra parte, por eso siempre es necesario enfocarse en los requerimientos que se solicitan.

## Ahora cuéntanos

¿Conoces sobre la arquitectura de microservicios? ¿Es requerida en tu industria?