[[Tema 1-Introducción a .NET]]

## Qué es ADO.NET?
Es un mapeador objeto-relacional para .NET. Proporciona soporte para la mayoría de gestores de bases de datos relacionales. 

El acceso a bases de datos relacionales está formado por dos entornos, el conectado y el desconectado. 

### Entorno conectado
Los usuarios están siempre directamente conectados a la fuente  de datos. Esto permite un mejor control de la concurrencia y datos constantemente actualizados, pero a cambio consume muchos recursos y limita la escalabilidad.

### Entorno desconectado
Se copian datos o tablas en local, se trabaja con la copia y después se sincroniza con la fuente de datos. Es muy cómodo si los datos solo necesitan lecturas, pero al no estar sincronizados no siempre se puede usar.