[[Tema 1-Introducción a .NET]]

Usaremos SQLClient y SQLTypes. Todo lo que empieza por SQL hace referencia a SQLServer. ADO.NET equivale a JDBC. 

Tiene dos entornos. El entorno conectado es muy similar a Java. El desconectado dice a la base de datos que base de datos se quiere usar, las vuelca en memoria y, cuando se acaba de operar, devuelve todos los datos a la base de datos. Esto da muchos problemas de concurrencia. Se utiliza para tablas que no varían, por ejemplo, los países del mundo.

