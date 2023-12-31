[[Xestión de Proxectos]]

## Esquema de gestión de la configuración en una PYME
El sistema software probado son los ficheros y código fuente y las ficheros de comandos para crear código objeto. Los documentos son la especificación de requisitos, la documentación de usuario, el plan de proyecto, los diseños y los módulos. 

Cuando hay un cambio se recurre a la gestión de configuración software. Es el responsable de gestión de la configuración el que se encarga de ello. Controla las versiones del producto, los registros de configuración y las solicitudes de cambio.

## Líneas base
### Línea base de requisitos
Cuando se tiene que hacer gestión de cambios en la especificación de requisitos aparecen el registro de cambios y las versiones y revisiones. Es el cliente el que realiza los cambios. 

### Línea base de producto
Cuando se tiene que hacer gestión de cambios en la especificación del producto, se activa la línea base de producto. En este proceso, se documentan y registran todos los cambios realizados en el producto, incluyendo las versiones y revisiones correspondientes. La responsabilidad de proponer modificaciones recae tanto en el equipo de desarrollo como en el cliente, asegurando una colaboración efectiva. La línea base de producto sirve como referencia para evaluar el impacto de los cambios, garantizando la coherencia y calidad del producto final. Además, facilita la trazabilidad y la comunicación entre todas las partes involucradas en el desarrollo del producto.

## Cambios aceptados
El cliente recurre al jefe del proyecto o a atención al cliente cuando quiere un cambio en los requisitos. Pasa por el jefe del proyecto (o por el director técnico) y se aceptan o rechazan los cambios. Luego se les comenta a los ingenieros de software que realizan los cambios, que serán cerrados por el jefe del proyecto, el cliente o el director técnico.

## Plantillas

### Apartados de la plantilla
1. Objeto: objetivo de la GCS, controlar el cambio.
2. Alcance: cuándo se debe aplicar. En este caso en los documentos de especificación de requisitos, del usuario y al software.
3. Procedimientos previos: ERS, procedimiento para informar de errores, procedimiento de atención al cliente.
4. Aspectos relevantes: ninguno.
5. Aprobaciones: persona que autoriza que esto se pueda usar en la empresa, en este caso el director general.
6. Responsabilidades: indica cuáles son las responsabilidades de cada rol. En este caso el jefe del proyecto y, en caso de ausencia, lo que diga atención al cliente.
7. Entradas del proceso: ECS y solicitudes de cambio.
8. Salidas del proceso: solicitudes de cambio rellenadas, versiones del producto y registros de configuración.
9. Mecanismos de control: indica quien realizará las auditorías.
10. GCS

### Apartado 10: GCS
1. ECS
	1. Documentación
	2. Software
2. Línea base
	1. Línea base de requisitos
	2. Línea base de productos
3. Registros de configuración
4. Gestión de cambios
	1. Registros de las solicitudes de cambio
	2. Análisis de las solicitudes de cambio
	3. Realización del cambio
	4. Cierre de las solicitudes de cambio
5. Gestión de versiones
	1. Numeración de versiones
	2. Entorno de trabajo

## Entornos de trabajo
En este ejemplo tenemos 3 entornos de trabajo diferentes:
+ **Entorno de desarrollo:** estructura en local donde se desarrolla y se hacen las pruebas unitarias.
+ **Entorno de pruebas:** estructura en red donde se hacen las pruebas de integración y sistema.
+ **Entorno de cliente:** producto consolidado entregado al cliente donde se hacen las pruebas de aceptación. Si hay que hacer cambios se copia al entorno de desarrollo.