[[Tema 9-ITIL]]

## Procesos
Son conjuntos estructurados de actividades diseñadas para alcanzar un objetivo específico. Convierten entradas en salidas definidas. Definen acciones, dependencias y secuencia. Pueden incluir cualquiera de los roles, responsabilidades, herramientas y controles de gestión necesarios para proporcionar las salidas de forma fiable. Pueden definir políticas, estándares, guías, actividades e instrucciones de trabajo. Deben supervisarse y documentarse y, una vez controlados, pueden repetirse y ser gestionados.

### Características
+ **Facilidad de medición:** capacidad de medir el proceso de forma relevante. Estas medidas estarán determinadas por el rendimiento.
+ **Resultados específicos:** proporciona un resultado específico que se debe poder identificar y contabilizar.
+ **Satisfacción de clientes:** proporcionan sus resultados primarios a un cliente o interesado (stakeholder) al que deben satisfacer en sus expectativas.
+ **Sensibilidad a detonantes:** tanto los procesos en curso como los iterativos deben poder trazarse hasta un detonante específico.

### Modelado
Los procesos se organizan alrededor de objetivos y sus principales salidas deberían estar determinadas por estos objetivos e incluir:
+ Medidas
+ Informes
+ Propuestas de mejora

Las salidas del proceso tienen que ajustarse a las normas operacionales derivadas de los objetivos del negocio. Un proceso es efectivo si se adapta a ellas. Si se realiza con el mínimo número de recursos es eficiente.

Las entradas del proceso son la información que se usa a lo largo del proceso y pueden ser las salidas de otro proceso anterior.

Las actividades o procesos dentro de un proceso se inician debido a un evento detonante (trigger), como por ejemplo la llegada de un input u otro evento. Los análisis, resultados y métricas del proceso deberían incluirse en informes periódicos de gestión y en las propuestas de mejora del proceso. Se utilizan plantillas.

## Funciones
Un función es un equipo o grupo de personas junto con las herramientas y otros recursos que utilizan para llevar a cabo uno o más procesos o actividades. En las organizaciones las funciones pueden desarrollarse en un único departamento/unidad o bien involucrar a varios. En organizaciones pequeñas una persona o grupo suelen realizar múltiples funciones. Proporcionan estructura y suelen optimizar los métodos de trabajo locales al centrar los esfuerzos en lograr los objetivos asignados a cada grupo o equipo.

### Funciones en ITIL
+ **Service Desk:** proporciona un único punto de contacto entre el proveedor del servicio y el usuario. Es el centro de todos los procesos que dan soporte al servicio.
+ **Gestión de operaciones TI:** : grupo o equipo formado por el personal que realiza las tareas diarias para mantener la infraestructura TI y permitir que los servicios TI estén disponibles.
+ **Gestión técnica:** grupo o equipo depositario del conocimiento técnico y la experiencia relacionada con la gestión de la infraestructura TI. Son los proveedores de los recursos técnicos necesarios para soportar el ciclo de vida de los servicios.
+ **Gestión de aplicaciones:** grupo o equipo depositario del conocimiento y la experiencia relacionada con la gestión software. Son los proveedores de los recursos necesarios para soportar el ciclo de vida de los servicios.

## Roles
Los roles son conjuntos de responsabilidades, actividades y autoridades asignadas a una persona o equipo. Los roles se definen normalmente para los procesos o las funciones. Indican qué papel desempeña cada persona, equipo o grupo de trabajo en los procesos que les atañen. Deben asignarse a individuos concretos. Una misma persona o equipo puede desempeñar múltiples roles dentro de la organización. Un mismo rol pueden tenerlo asignado diferentes personas o equipos.

Los roles específicos de la Gestión de Servicios requieren unas habilidades, atributos y competencias, específicos de forma que el personal implicado pueda trabajar de manera efectiva y eficiente. Por ejemplo, habilidades de negociación o habilidades de gestión.

Los roles se dividen en 2 categorías principales:
+ **Genéricos:** gestor de un proceso o el propietario de un servicio.
	+ **Responsable de servicio:** responsable de un servicio específico de la organización, independientemente de donde residan los componentes tecnológicos de soporte, los procesos y las capacidades.
	+ **Responsable de proceso:** responsable de asegurar que un proceso cumple con su propósito (fit for purpose), que se realiza conforme a los estándares acordados y documentados y satisface los objetivos de su definición.
	+ **Gestor de proceso:** responsable de la gestión operacional de un proceso.
	+ **Profesional o trabajador:** responsable de la realización de una o más actividades de un proceso.
+ **Específicos:** de una etapa concreta del ciclo de vida o de un proceso concreto.

## Matriz RACI
Es una herramienta gráfica que suelen utilizar las organizaciones para definir los roles y responsabilidades de sus procesos y actividades. Las filas representan un conjunto de actividades. Las columnas identifican a las personas o equipos que toman las decisiones, llevan a cabo las actividades o proporcionan las entradas. En cada celda de la matriz RACI se especifica un subconjunto de los cuatro roles considerados:
+ **R, Responsible:** responsable del trabajo.
+ **A, Accountable:** responsable de calidad.
+ **C, Consulted:** consultor.
+ **I, Informed:** encargado del progreso de la actividad.

Por ejemplo:

| Actividad    | Director del Servicio | Gestor de Problemas | Gestor de Seguridad | Gestor de Configuraciones |
|--------------|------------------------|----------------------|----------------------|---------------------------|
| Actividad 1  | A                      | R                    | I                    | C                         |
| Actividad 2  | A                      | R                    | C                    | C                         |
| Actividad 3  | I                      | A                    | R                    | IC                        |
| Actividad 4  | I                      | R                    | A                    | CI                        |
| Actividad 5  |                        | RA                   | C                    | I                          |


| Actividad                                  | Dirección del Hotel | Gerente o Responsable Económico | Jefe de Recepción | Recepcionistas |
|--------------------------------------------|---------------------|---------------------------------|-------------------|----------------|
| Revisar los precios de la competencia      | I                   | A, C, I                         | R                 |                |
| Controlar la ocupación del hotel            | I                   |                             | A, R                |        R        |
| Publicar ofertas en webs de reservas       | I                   | A, C, I                         | R                 | R              |
| y buscadores                                |                     |                                 |                   |                |
| Dar parte diario a las autoridades         | A, I                   |                            | R                 | R              |
| sobre la identidad de los clientes alojados|                     |                                 |                   |                |
| Atender las quejas o sugerencias            | C, I                |                            | A, R                 |     R           |
| de los clientes                             |                     |                                 |                   |                |
| Facturación diaria                          |  I                | A, I                               | R                 | R              |
