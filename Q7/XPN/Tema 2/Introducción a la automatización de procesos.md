[[Tema 2-Automatización de procesos]]

## Cuándo debemos automatizar un proceso?
Un proceso se debe automatizar cuando:
+ Está bien definido.
+ Se instancia muy frecuentemente.
+ Pueden realizarse instancias de forma concurrente.
+ Tiene tareas de aprobación.
+ Tiene tareas que no necesitan intervención humana.
+ Debe ser consistente y genera métricas constantemente.
+ Es crítico, ya sea por legislación vigente, normativas de la empresa, poca tolerancia a fallos humanos, etc.

### Cómo se automatiza?
Para automatizar un proceso se puede recurrir a un motor de automatización, por ejemplo, BonitaSoft. Utiliza BPMN 2.0 y trabaja en plataformas Java. 

## Componentes de la automatización
Un proceso automatizado está formado por:
+ **Modelo del proceso:** son las actividades, roles y workflow.
+ **Motor de ejecución:** es el propio motor de automatización, que ejecuta el flujo definido en el modelo.
+ **Base de datos:** es donde se almacena la información.
+ **Vistas:** son las interfaces con las que interactúan los usuarios, como los formularios.
+ **Usuarios y roles:** son los permisos que indican quien puede interactuar con cada parte del proceso.
+ **Seguridad:** es la garantía de que los datos y acciones estén protegidos, que va ligado a los roles.
+ **Integración con otros sistemas:** es la conexión con otros sistemas de la organización, como el sistema de calendario, notificaciones, etc.
