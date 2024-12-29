[[Tema 1-Introducción a .NET]]

## Qué es ADO.NET?
ADO.NET es un mapeador objeto-relacional. Proporciona soporte para la mayoría de gestores de bases de datos relacionales. Está formado por dos entornos.

### Entorno conectado
Los usuarios están siempre directamente conectados a la fuente  de datos. Esto permite un mejor control de la concurrencia y datos constantemente actualizados, pero a cambio consume muchos recursos y limita la escalabilidad. Los recursos se mantienen en el servidor hasta cerrar la conexión.

### Entorno desconectado
Se copian datos o tablas en local, se trabaja con la copia y después se sincroniza con la fuente de datos. Es muy cómodo si los datos solo necesitan lecturas, pero al no estar sincronizados no siempre se puede usar.