[[Tema 1-Introducción a la arquitectura de software]]

## 1.Qué son los requisitos no funcionales?
Los requisitos no funcionales son las propiedades y restricciones de un sistema, como la fiabilidad, el tiempo de respuesta, la capacidad de almacenamiento, etc. Afectan a todo el sistema, no a componentes concretos. Pueden incluir restricciones de entorno o de negocio, como las tecnologías que se pueden usar, los ciclos de vida que se usan en el proyecto, etc.

Son muy importantes, incluso más que los requisitos funcionales, ya que si no se cumplen el software puede no funcionar. En base a ellos se puede analizar si es posible realizar ciertos requisitos funcionales o si se deben implementar ciertas funcionalidades para que el software funcione adecuadamente.

### 1.1.Verificación y validación
Es muy difícil validar los requisitos funcionales. Debe validarse todo el conjunto de requisitos no funcionales para comprobar que sean consistentes y realistas. Por ejemplo, para que un sistema sea seguro se emplearán bastantes recursos, por lo que afectará a su eficiencia. Se deben balancear la eficiencia y la seguridad.

Además se debe comprobar que sean verificables. Para ello deben adaptarse a los escenarios en los que se probarán.

## 2.Métricas
Los requisitos no funcionales deben ser cuantificables. Algunos ejemplos de métricas son:

| **Requisito no funcional** | **Medida**                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Velocidad                  | Transacciones por segundo, tiempo de respuesta, tiempo de recarga                                                               |
| Tamaño                     | Píxeles, megabytes                                                                                                              |
| Facilidad de uso           | Tiempo de entrenamiento, número de páginas de ayuda de usuario                                                                  |
| Fiabilidad                 | Tiempo medio de fallo, probabilidad de no-disponibilidad                                                                        |
| Robustez                   | Tiempo de reinicio después de un fallo, porcentaje de eventos que pueden fallar, probabilidad de perdida de datos tras un fallo |
| Portabilidad               | Número de plataformas objetivo, porcentaje de elementos dependientes de la plataforma                                           |

## 3.Clasificación
Los requisitos no funcionales se dividen en:
+ Requisitos de producto
	+ Usabilidad
	+ Eficiencia
		+ Rendimiento
		+ Recursos
	+ Confiabilidad y seguridad
		+ Confiabilidad
		+ Disponibilidad
		+ Fiabilidad
		+ Safety
		+ Security
+ Requisitos de organización
	+ De entorno
	+ Operacionales
	+ De desarrollo
+ Requisitos externos
	+ De regulaciones
	+ Éticos
	+ De legislación
		+ Contables
		+ De seguridad

### 3.1.Confiabilidad
Es el grado de confianza que tiene un usuario con el software o sistema.

#### 3.1.1.Motivos de fallos
Un usuario pierde confianza si el sistema falla muy a menudo. Las causas más habituales son:
+ **Fallos hardware:** fallos en el diseño o en la fabricación de componentes físicos o fin de la vida útil de estos.
+ **Fallos software:** errores de especificación, diseño o desarrollo del software.
+ **Fallos operativos:** fallos por culpa del entorno.

#### 3.1.2.Mejora de la confiabilidad
Podemos incrementar la confiabilidad mediante ciertas técnicas:
+ **Evitación de fallos humanos:** minimizar la posibilidad de que los fallos humanos causen fallos en el sistema.
+ **Detección y eliminación:** uso de técnicas de validación y verificación para incrementar la posibilidad de detectar y corregir errores antes de que el sistema se empiece a usar.
+ **Tolerancia a fallos:** técnicas usadas para evitar que el sistema falle en tiempo de ejecución.

### 3.2.Fiabilidad
Es la capacidad que tiene un sistema para ofrecer su funcionalidad cuando lo necesita.

#### 3.2.1.Métricas de fiabilidad
Podemos medir ciertos parámetros para cuantificar la fiabilidad:
+ **Número de fallos:** cantidad de errores del sistema aceptables durante su uso.
+ **Probabilidad de fallo a demanda:** probabilidad de que el sistema falle cuando se requiere su servicio.
+ **Ratio de ocurrencia de fallos:** número de fallos que ocurren por conjunto de operaciones.
+ **Tiempo medio de fallo:** promedio de tiempo que tarda en fallar un sistema.

### 3.3.Disponibilidad
Fracción de tiempo que necesita un sistema para poder prestar un servicio. Se tiene en cuenta el tiempo que tarda un sistema en recuperarse tras un reinicio o fallo. Por ejemplo, una disponibilidad de 0.5 significa que está disponible media hora por cada hora.

### 3.4.Safety
Es la capacidad de un sistema para operar sin que ocurran fallos que afecten gravemente al sistema. Para ello es necesario que sea fiable y esté disponible.

En sistemas complejos los accidentes suelen ser causados por una cadena de fallos. Si un sistema tiene un single point of failure es más probable que ocurran fallos catastróficos. Pese a todo, es imposible garantizar una safety absoluta.

#### 3.4.1.Formas de aumentar la safety
Se puede mejorar mediante ciertas técnicas:
+ **Evitación de riesgos:** diseñar el sistema tratando de evitar la máxima cantidad de riesgos posibles.
+ **Detección y eliminación de riesgos:** el sistema debe eliminar los riesgos antes de que causen daños mayores.
+ **Contención de daños:** el sistema debe incluir mecanismos que reduzcan los daños en caso de accidentes.

### 3.5.Security
Es la capacidad de un sistema para protegerse de intrusiones o ataques. Es imprescindible en sistemas que utilicen internet. La capacidad de seguir en funcionamiento al recibir ataques, por ejemplo DoS, se llama survivability.

#### 3.5.1.Tipos de amenazas
Las amenazas pueden afectar a:
+ **Confidencialidad:** revelación de información de datos confidenciales del sistema.
+ **Integridad:** alteración del sistema mediante ataques de fabricación o modificación que afectan a la integridad de los datos.
+ **Disponibilidad:** denegaciones de servicio.

#### 3.5.2.Formas de aumentar la security
Se puede mejorar mediante ciertas técnicas:
+ **Evitación de vulnerabilidades:** diseñar el sistema tratando de evitar posibles vulnerabilidades.
+ **Detección y eliminación de ataques:** neutralizar vulnerabilidades según se detecten.
+ **Limitación de la exposición y recuperación:** el sistema debe minimizar la cantidad de ataques que le puede llegar.