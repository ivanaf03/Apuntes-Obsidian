[[Tema 1-Introducción a la arquitectura de software]]
$\space$
## 1.Qué son los requisitos no funcionales?
Los requisitos no funcionales son las propiedades y restricciones de un sistema, como la fiabilidad, el tiempo de respuesta, etc. Afectan a todo el sistema, no a componentes concretos. Además pueden incluir restricciones dependiendo del entorno, negocio, etc.

Son más críticos que los requisitos funcionales. Si no se cumplen, el software puede no funcionar. Permiten analizar si se pueden implementar ciertos requisitos funcionales.
$\space$
### 1.1.Validación y verificación
Es muy difícil validar los requisitos no funcionales. Deben validarse en conjunto para ver si son consistentes entre ellos y realistas. Por ejemplo, para que un sistema sea seguro se emplearán bastantes recursos, por lo que afectará a su eficiencia. Se deben balancear la eficiencia y la seguridad.

También hay que asegurarse que sean verificables. Para ello hay que tener en cuenta en que escenarios se probarán.
$\space$
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
$\space$
## 3.Clasificación

![[RNF.png]]
$\space$
### 3.1.Confiabilidad y seguridad
La confiabilidad es el grado de confianza que tiene un usuario con el sistema. Se basa en 4 requisitos no funcionales:

![[confiabilidad.png]]
$\space$
#### 3.1.1.Fallos más habituales
Los fallos más habituales son:
+ **Fallos hardware:** fallos en el diseño o fabricación de los componentes físicos.
+ **Fallos software:** errores no detectados en la especificación, diseño o desarrollo.
+ **Fallos operativos:** fallos en el entorno.
$\space$
#### 3.1.2.Cómo se puede incrementar la confiabilidad?
Para que un sistema sea más confiable se puede usar:
+ **Fault avoidance:** minimizar la posibilidad de que los fallos humanos se conviertan en fallos en el sistema.
+ **Detección y eliminación:** técnicas de validación y verificación para incrementar la posibilidad de detectar y corregir faltas o errores antes de que el sistema esté operativo.
+ **Fault tolerance:** técnicas en tiempo de ejecución 
$\space$
#### 3.1.3.Fiabilidad
La fiabilidad es la capacidad de un sistema para ofrecer se funcionalidad como se necesita. Se debe medir, por lo que se debe expresar cuantitativamente:
+ **Número de fallos:** cantidad de fallos aceptables durante el tiempo de uso.
+ **Probabilidad de fallo a demanda:** probabilidad de que el sistema falle cuando se requiere su servicio.
+ **Ratio de ocurrencia de fallos:** número de fallos por cada conjunto de operaciones.
+ **Tiempo medio de fallo:** promedio de tiempo que tarda en fallar un sistema.
$\space$
#### 3.1.4.Disponibilidad
La disponibilidad es la capacidad de un sistema para ofrecer sus funcionalidades cuando se necesitan. Mide la cantidad de tiempo que un sistema tarda en prestar servicio. Se debe tener en cuenta el tiempo necesario para reparar y reiniciar el sistema en caso de fallo.
$\space$
#### 3.1.4.Safety
La safety es la capacidad de un sistema para operar sin que se produzcan fallos catastróficos. Para ello es necesario que sea fiable y que esté disponible.

En sistemas complejos los fallos catastróficos suelen ser causados por cadenas de fallos. Si un sistema tiene un single point of failure es más probable que ocurran fallos catastróficos. 

Para incrementar la safety podemos utilizar una serie de técnicas:
+ **Hazard avoidance:** el sistema debe estar diseñado tratando de evitar la máxima cantidad de riesgos.
+ **Detección y eliminación de riesgos:** el sistema debe eliminar los riesgos antes de que causen daños mayores.
+ **Contención de daños:** el sistema debe incluir mecanismos que minimicen los daños en caso de accidentes.
$\space$
#### 3.1.5.Security
La security es la capacidad de un sistema para protegerse de intrusiones o ataques. Es esencial si el sistema utiliza internet. Se denomina survivability la capacidad de un sistema para seguir en funcionamiento tras recibir ataques. Las amenazas pueden atacar a la confidencialidad de los datos, a la integridad del sistema o a la disponibilidad del sistema. 

Para incrementar la security podemos usar técnicas como:
+ **Evitación:** diseñar el sistema de forma que no se puedan dar ciertas vulnerabilidades.
+ **Detección y eliminación:** diseñar el sistema de forma que las vulnerabilidades se detecten y se neutralicen antes de que se vuelvan problemas.
+ **Limitación de la exposición y recuperación:** diseñar el sistema para minimizar el alcance de los ataques con éxito.