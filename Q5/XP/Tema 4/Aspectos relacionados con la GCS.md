[[Tema 4-Gestión de la configuración software]]

## Actividades relacionadas
### Control de versiones
Consiste en mantener un historial de versiones por las que pasan los componentes de un producto que permita recuperarlas.

Facilita la GCS. Permite, para cada ECS, saber cuál es la última versión, donde están, la relación que hay entre ellas... Un ejemplo es el uso de Git. Facilita el control de cambios porque permite realizar cambios en versiones que no sean la última.

Una versión es una instancia del ECS en un momento puntual del desarrollo, que se almacena en un repositorio y que puede ser recuperada en cualquier momento. Una revisión es un cambio menor centrado en un aspecto específico del software. Se suelen nombrar como `VERSION.REVISIÓN`, por ejemplo, 1.3, 4.1, 2.5...

Para crear una nueva revisión de un ECS se suele realizar una modificación sobre la versión más reciente. Esto va formando una cadena, conocida como cadena de revisión. Se representa como un grafo llamado grafo de evolución o revisión (como el de GitHub).

El modelo de trabajo en general es:
![[modelo de ttrabajo.png]]
Las herramientas de control de versiones ayudan a crear, identificar y almacenar nuevas versiones mientras mantienen las anteriores. Sin embargo, no físicamente (solo la primera o la última). En su lugar guardan el historial de cambios.

Se conoce como delta la secuencia de operaciones que aplicadas sobre la revisión 1 dan la revisión 2. Pueden ser:

Según su dirección:
+ directos 
+ inversos

Y según su localización:
+ separados
+ mezclados

Las variantes son versiones de un ECS que coexisten pero son diferentes. Buscan que un objeto satisfaga diferentes requisitos al mismo tiempo (las ramas de Git). Pueden ser:
+ temporales
+ de usar y tirar
+ permanentes
	+ de requisitos de usuario
	+ de plataforma

Al crear ramas vamos a tener configuraciones alternativas. Los ECS se cada configuración se pueden conseguir asociándoles atributos o creando configuraciones específicas. La herramienta Make ayuda a ello.

Una release es una configuración entregable. La GCS también controla la gestión e instalación de releases.

### Construcción
Consiste en gestionar la compilación y enlazado de los distintos componentes del producto de la forma más eficiente posible. Es necesario saber que componentes enlazar, en que versión y donde están. Esto se saca del control de versiones y de la configuración.

Herramientas como make permiten compilar y enlazar los ECS necesarios una vez especificadas las diferentes configuraciones del producto.

### Gestión de problemas
Consiste en realizar un seguimiento de la evolución de los problemas que afectan al producto. Es complementaria al control de cambios, ya que estos suelen aparecer o por cambios en los requisitos o por problemas. 

Esta actividad gestiona desde los problemas en la fase de pruebas como en los informes que se entregan al usuario. Las tareas que realiza esta actividad son:
+ Admisión, valoración y registro de informes de incidencias.
+ Asignación del problema a un responsable.
+ Asociación de información al problema.
+ Monitorización del problema.
+ Registro de la corrección del problema.
+ Creación de informes de los problemas.

### Control del trabajo en equipo
Consiste en controlar las interacciones que se producen entre los múltiples desarrolladores de un producto. Sobre todo afecta a la compartición de componentes.

La GCS facilita el trabajo en equipo. Al compartir elementos de trabajo existe el riesgo de sobreescritura de los cambios. Se soluciona con un desarrollo en paralelo y haciendo un merge de los cambios.

### Otros aspectos
+ **Metodologías:** hay que integrar la GCS con las metodologías que se usen, ya que las fases, productos, etc afectan a la GCS.
+ **Entorno de desarrollo:** las herramientas de GCS deben integrarse en las herramientas de desarrollo.
+ **Organización:** pueden aparecer nuevas políticas, procedimientos, roles y responsabilidades que deben integrarse en la organización del proyecto.
+ **Calidad:** una buena GCS contribuye a una buena calidad.