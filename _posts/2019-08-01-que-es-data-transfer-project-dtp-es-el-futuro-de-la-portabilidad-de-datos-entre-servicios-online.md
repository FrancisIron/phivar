---
title: "¿Qué es Data Transfer Project (DTP)?, el futuro de la portabilidad de datos entre servicios online"
author: fierro
layout: post
comments: true
image: assets/images/articulo-dtp.jpg
categories: [Actualidad, Articulos, Google, Negocios, Noticias, Tecnología]
tags: destacado
---
**Data Transfer Project** (o DTP) es una iniciativa de código abierto que ofrece estandarizar la portabilidad de datos entre múltiples plataformas en línea, intentando solucionar con esto uno de los grandes problemas que tienen los usuarios cuando quieren migrado datos. Nos referimos al **Data Lock-in**, la imposibilidad de obtener todos los datos que tenemos almacenados en un servicio para irnos a otro. El proyecto fue lanzado y presentado por Google el 20 de julio del 2018, y actualmente se ha asociado con Facebook, Microsoft, Twitter y recientemente Apple.

Esta idea se remonta a 2007 cuando surgió la **[Data Liberation Font](http://dataliberation.blogspot.com/)** un grupo de ingenieros de Google cuyo objetivo es _facilitar a los usuarios la entrada y salida de sus datos de los productos de Google._ Gracias a ellos es que disponemos de **[Google Takeou](https://takeout.google.com/)**t, una herramienta para los usuarios que permite hacer copias de seguridad de tus archivos en todos los servicios de Google. 

Recientemente, este proyecto presento la especificación y arquitectura que permitirá llegar a un API común para la transferencia de datos de usuario entre servicios. La clave aquí es poder definir una comunicación directa y sin intermediarios, creando de paso un ecosistema de formato común de datos.

## El futuro de la portabilidad Service-to-Service

La meta final de todo esto, es que los usuarios sean capaces de transferir sus datos desde un servicio a otro, sin la necesidad de apoyarse de un intermediario o de tener que descargar y volver a subir todos sus datos.

Para facilitar la complicada misión de portabilidad de datos, **Data Transfer Project** define una serie de _adapters_ (adaptadores) que transformen los formatos propietarios a una serie de _Data Models_ (modelo de datos) común. Esto permitirá que la transferencia de datos pueda hacerse desde el propio proveedor del servicios a otro manteniendo el control sobre la seguridad e integridad de los datos.

<p><div class='img'><img src='{{site.baseurl}}/assets/images/ilustracion-dtp1.png'/><span>Ejemplo de portabilidad de datos, antes del Data Transfer Project y como sería estando implementado.</span></div></p>

Ahora bien, estos _Data Models_ (modelos de datos) están limitados en función de la información que se puede compartir de un servicio a otro, ya que es imposible modelar toda la información, pero los distintos casos de uso ya creados como la migración de fotos o contactos, cubre de por sí, un amplio horizonte de funcionalidades esperadas. Para el resto de información aun habrá que seguir usando mecanismos que incorporen metadata más especifica.

## ¿Cómo funciona? La arquitectura detrás de Data Transfer Project

Existen 3 componentes fundamentales descritos en el [paper](https://datatransferproject.dev/dtp-overview.pdf) de Data Transfer Project:

  * **Data Models**, que proporcionan un formato común para transferir los datos.
  * **Adapters**, son métodos que convierten cada dato propietario y a su vez, posibilitan la autenticación e integridad del sistema y los datos.
  * **Task Management** que realiza las tareas de fondo para ejecutar la migración de datos.

La idea es que por medio de los Data Models podamos definir el formato de datos que queremos intercambiar. Actualmente se puede consultar los existentes en el GitHub del proyecto: emails, fotos, calendarios, tareas, etc.

Con los Adapters podemos hacer la traducción entre los datos dados de un proveedor concreto (la API del servicio) a los Data Models de intercambio de DTP. Además de la transformación de los datos, existe otro tipo de Adapters que se ocupan de la autenticación de los datos. Aunque OAuth ha sido el proveedor más extendido, DTP es agnóstico en el tipo de autenticación.

Por último, el conjunto de tareas necesarias para realizar la carga de la portabilidad de datos reside en el otro gran componente de Tasks. Estos se encargan de realizar los llamados entre los distintos Adapters, realizar la lógica de reintento, gestionar los rate limits, paginación, notificaciones, etc.

<p><div class="img"><img src='{{site.baseurl}}/assets/images/ilustracion-dtp2.png'><span>Arquitectura y flujo de trabajo de DTP</span></div></p>

¿Qué les pareció?, ¿han tenido la engorrosa misión de tener que migrar los contactos cuando han querido cambiar de servicio?. Cuentenme en los comentarios, los estaré leyendo. 

Hasta la próxima.