[[Tema 4-Gestión de la configuración software]]

### Actividades relacionadas
Las herramientas CASE suelen incluir:

##### Control de versiones
Consiste en mantener un historial de versiones por las que pasan los componentes de un producto que permita recuperarlas.

Facilita la GCS. Permite, para cada ECS, saber cuál es la última versión, donde están, la relación que hay entre ellas... Un ejemplo es el uso de Git. Facilita el control de cambios porque permite realizar cambios en versiones que no sean la última.

Una versión es una instancia del ECS en un momento puntual del desarrollo, que se almacena en un repositorio y que puede ser recuperada en cualquier momento. Una revisión es un cambio menor centrado en un aspecto específico del software. Se suelen nombrar como VERSION.REVISIÓN, por ejemplo, 1.3, 4.1, 2.5...

##### Construcción
Consiste en gestionar la compilación y enlazado de los distintos componentes del producto de la forma más eficiente posible.

##### Gestión de problemas
Consiste en realizar un seguimiento de la evolución de los problemas que afectan al producto.

##### Control del trabajo en equipo
Consiste en controlar las interacciones que se producen entre los múltiples desarrolladores de un producto. Sobre todo afecta a la compartición de componentes.