[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Opción 1
![[distribución de capas 1.png]]

Problemas:
+ Al hacer cambios en la capa modelo tenemos que reinstalar todo en todas las máquinas cliente.
+ No es seguro, se accede al código y a la base de datos desde el cliente.

La solución es separar en un modelo en servidor intermedio y clientes de escritorio.

### Opción 2
![[distribución de capas 2.png]]

Problemas:
+ Al querer hacer un cambio en la interfaz gráfica tenemos que cambiarla en todos los clientes. 

Se soluciona con interfaces web. La ventaja de estas aplicaciones de escritorio o *standalone* es que sus funcionalidades en local siempre están disponibles.

### Opción 3
![[distribución de capas 3.png]]

Las aplicaciones Web se instalan en un servidor de aplicaciones. Los cambios que se hagan tanto en la interfaz gráfica como en la capa modelo sólo requieren de instalar la aplicación en el servidor de aplicaciones.

Ventajas:
+ Se puede crear un clúster de máquinas con un balanceador de carga, por ejemplo, si tenemos 3 servidor de aplicación en el clúster, podemos mandar la primera que llegue al primero, la segunda al segundo... Se suele utilizar el algoritmo de Round Robin.
+ Añadir más máquinas al clúster nos proporciona buena escalabilidad.
+ En cuanto a disponibilidad, a pesar de que una máquina se caiga, quedan otras funcionando.

### Opción 4
![[distribución de las capas 4.png]]

Separar los servidores aplicación en 2 capas diferentes nos permite utilizar diferentes tecnologías en ellas.

### Opción 5
![[distribución de capas 5.png]]

Esta distribución la utilizan las aplicaciones SPA (*Single Page Aplicaction*). El navegador accede al servidor web para obtener el código de la aplicación web. La aplicación se ejecuta dentro del navegador de la máquina cliente.