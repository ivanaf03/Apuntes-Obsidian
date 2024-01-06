[[Tema 11-Gestión de la seguridad]]

## Seguridad
Debemos preservar:
+ **Confidencialidad:** que los datos solo los pueda ver alguien que tenga permiso para verlos.
+ **Integridad:** los datos deben estar completos y correctos.
+ **Disponibilidad:** los datos deben estar siempre disponibles si son requeridos.

Se parte del principio "que todo lo que no esté en la lista de lo que se puede hacer, se prohíba".

### Dominios de la ISO
+ Políticas de seguridad
+ Organización
+ Seguridad de los RRHH
+ Clasificación y control de activos
+ Control de acceso
+ Criptografía
+ Seguridad física y ambiental
+ Operaciones de seguridad
+ Seguridad de las comunicaciones
+ Adquisición, desarrollo y mantenimiento de sistemas
+ Relaciones con proveedores
+ Gestión de incidentes
+ Continuidad del negocio
+ Cumplimiento legal

El cumplimiento legal es complejo. La ISO tiene que encajar con la legislación estatal. Muchas actualizaciones se hacen para intentar cumplir con las normativas de los diferentes países. Esto mismo pasa si choca con la normativa de la empresa. 

### Seguridad física y del entorno
+ Control de accesos
+ Sensores de temperatura, humedad...
+ Seguridad en accesos de mercancías
+ Seguridad perimetral
+ Energía
+ Climatización
+ Compartimentación
+ Control de plagas

### Gestión energética
+ Power Usage Effectiveness
$$PUE=Carga\ total\ consumida/Carga\ TI$$
+ Data Center Efficiency
$$DCE=\%\ energético\ consumido\ por\ TI$$
Cuanto mayor sea el PUE y menos el DCE, menos eficiente será nuestro CPD.

### Aspectos contractuales
Es importante tener cuidado con la compra de tecnología, la prestación de servicios de mantenimiento y la externalización.

El SLA, Acuerdo de Nivel de Servicio, es un contrato formal que especifica los niveles de servicio que se compromete a proporcionar un proveedor de servicios a sus clientes. Este acuerdo define los parámetros clave que deben cumplirse, tales como la calidad del servicio, el tiempo de respuesta, el tiempo de actividad, y otros indicadores de rendimiento.

Se debe cuidar:
+ Servicios de terceros, niveles y condiciones de reposición de materiales y traslado de técnicos en incidencias.
+ Criticidad de eventos y tiempos de respuesta.
+ Cláusulas de auditabilidad para verificar la seguridad.
+ La declinación de responsabilidades por parte del proveedor en caso de incidentes de seguridad no es aceptable.
+ Políticas de gestión de cambios acordes con las nuestras.
+ Condiciones para la continuidad de servicios.
+ Penalizaciones en caso de deficiencias en el servicio.

### Seguridad lógica
Se debe mantener securizado mediante:
+ Actualización de sistemas.
+ Buena configuración de seguridad.
+ Monitorización operacional.
+ Operaciones de seguridad.
+ Segregación de entornos.
+ Datos de los entornos de desarrollo y/o pruebas.
+ Cifrado de datos y certificados.
+ Compartimentado de la red.
+ Gestión de cambios.
+ Control de accesos privilegiados.
+ Control de accesos remotos de terceros.
+ Control en entornos multicliente.

Al virtualizar la seguridad en los hipervisores de virtualización no implica la seguridad en los hosts. Los fallos de seguridad en la infraestructura de virtualización comprometen la seguridad de los equipos virtualizados. Para securizarlo:
+ Se requieren controles de acceso.
+ Hay que disponer de pistas de auditoría para monitorizar el acceso.
+ No se debe utilizar el mismo hipervisor de virtualización para diferentes zonas de seguridad.
+ Las áreas de seguridad deben limitarse mediante firewalls físicos.
+ Se debe segmentar la red de administración de virtualización.
+ La infraestructura de administración es más crítica que el servidor más crítico que soporte.

## Gestión de incidentes
Un incidente es un único evento o serie de eventos de seguridad de la información inesperados o no deseados, que tienen una probabilidad significativa de comprometer las operaciones empresariales y de amenazar la seguridad de la información.

Los más habituales son incendios por problemas eléctricos y fallos de backups.

Debería existir una política de seguridad de la información (responsables y método de comunicación), mecanismos de control (identificación temprana y acciones a tomar de prevención), planes de acción (cómo actuar ante diferentes incidentes) y auditorías e informes de incidencias de seguridad (recopilando toda la información sobre el tratamiento de las incidencias que han ocurrido). Si existen brechas de seguridad con datos personales involucrados, hay que comunicarlo a la Agencia Española de Protección e Datos en 72h.

### Auditorías de seguridad
Las auditorías pueden ser:
+ Físicas y del entorno
	+ Accesos y control de acceso
	+ Climatización
	+ Alarmas y monitorización
	+ Gestión energética
+ Aspectos contractuales
	+ Seguridad de accesos externos
	+ Externalización total o parcial
+ Lógica
	+ Cifrado
	+ Actualizaciones
	+ Privilegios
	+ Compartimentación de la red
