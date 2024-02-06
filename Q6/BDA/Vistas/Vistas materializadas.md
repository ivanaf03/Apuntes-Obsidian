[[Vistas]]

## ¿Qué son las vistas materializadas?
También se llaman `snapshots`. Almacenan el resultado de la consulta en disco. Las consultas son más rápidas, aunque ocupan espacio y hay que actualizar el contenido. 

Oracle permite especificar cuando materializar la vista y cuando refrescar esos datos para mantenerlos sincronizados con las tablas base.

La materialización puede ser:
+ **Inmediata:** cuando se define.
+ **Aplazada:** en el primer refresco.
+ **Prebuilt table:** utilizando una tabla preexistente.