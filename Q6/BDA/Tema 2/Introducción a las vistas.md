[[Tema 2-Vistas]]
$\space$$\space$
## 1.Qué es una vista?
Una vista es una tabla virtual generada a partir de la ejecución de varias consultas sobre una o más tablas.
$\space$$\space$
### 1.1.Vistas en la arquitectura ANSI/SPARC
Con respecto a la arquitectura ANSI/SPARC, las vistas permiten:
+ Definir diferentes esquemas externos.
+ Ofrecer ofrecer a cada usuario o rol solo la parte de datos que necesitan.
+ Conseguir interdependencia lógica, mostrando a las aplicaciones vistas en lugar de tablas completas para evitar que cambios en el nivel conceptual afecten a aplicaciones y a usuarios.
$\space$$\space$
### 1.2.Tablas en SQL y en SGBD relacionales
Las tablas almacenan la definición en el catálogo y los datos en el espacio de datos. Las tablas pueden ser:
+ **Permanentes:** mantienen la definición en el catálogo y los datos almacenados. Pueden ser accedidos por otros usuarios o sesiones.
+ **Temporales:** mantienen la definición también, pero los datos se eliminan al acabar la sesión en la que se crearon. A menos que se indique lo contrario explícitamente, no pueden ser accedidas por otros usuarios.
$\space$$\space$
### 1.3.Vistas en SQL y en SGBD relacionales
Las vistas almacenan la definición en el catálogo, pero no almacenan datos. Están formadas por su nombre, una lista de atributos o columnas y la definición, que es una sentencia `select`.

Existen un tipo especial de vistas, las vistas materializadas que sí almacenan los datos en el espacio de datos.