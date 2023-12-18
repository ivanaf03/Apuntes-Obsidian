[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

## Opción 1
![[distribución de capas 1.png]]

### Problemas
+ Al hacer cambios en la capa modelo tenemos que reinstalar todo en todas las máquinas cliente.
+ No es seguro, se accede al código y a la base de datos desde el cliente.

### Soluciones
+ Meter la capa modelo en un servidor intermedio, por tanto los clientes solo dispondrían de interfaz gráfica.

## Opción 2
![[distribución de capas 2.png]]

Se añaden una capa de acceso a servicios y una capa servicios para poder comunicar el servidor. Se conoce como arquitectura en 3 capas y a las aplicaciones como standalone (aplicaciones de escritorio).

### Ventajas
+ Permiten utilizar parte de sus funcionalidades en local.

### Problemas
+ Al querer hacer un cambio en la interfaz gráfica tenemos que cambiarla en todos los clientes. 

### Soluciones
+ Usar interfaces web. Lo bueno de las aplicaciones standalone es que permiten el uso de algunas funcionalidades aunque no se disponga de conexión.

## Opción 3
![[distribución de capas 3.png]]

Las aplicaciones web se instalan en un servidor de aplicaciones web.

### Ventajas
+  Los cambios que se hagan tanto en la interfaz gráfica como en la capa modelo sólo requieren de reinstalar la aplicación en el servidor de aplicaciones.
+ Se puede crear un clúster de máquinas con un balanceador de carga, por ejemplo, si tenemos 3 servidores de aplicación en el clúster, podemos mandar la primera petición HTTP que llegue al primero, la segunda al segundo... Se suele utilizar el algoritmo de Round Robin. 
+ Añadir más máquinas al clúster nos proporciona buena escalabilidad.
+ En cuanto a disponibilidad, a pesar de que una máquina del clúster se caiga, quedan otras funcionando.

## Opción 4
![[distribución de las capas 4.png]]

A esta distribución se le conoce como arquitectura en 4 capas.

### Ventajas
+ La capa servicios se puede implementar utilizando tecnologías de desarrollo web dentro del servidor de aplicaciones web.
+ Permite que la capa interfaz y la capa modelo se implementen con tecnologías diferentes.
+ Permite que aplicaciones remotas utilicen la capa modelo.

## Opción 5
![[distribución de capas 5.png]]

Esta distribución la utilizan las aplicaciones SPA (Single Page Application). Las SPA son aplicaciones web que funcionan en una sola página HTML inicial y utilizan JavaScript para cargar dinámicamente contenido y actualizar la interfaz de usuario en respuesta a las acciones del usuario, todo sin requerir la carga completa de nuevas páginas desde el servidor. Por ejemplo, Google Maps.

### Ventajas
+ Los cambios en la interfaz gráfica solo requieren reinstalar la aplicación en el servidor web.
+ Los cambios en la capa modelo solo requieren reinstalar la aplicación en el servidor de aplicaciones.



