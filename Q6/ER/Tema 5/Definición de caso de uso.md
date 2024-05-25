[[Tema 5-Casos de uso]]
$\space$
## 1.Actores y usuarios
Un usuario no es lo mismo que un actor. Un usuario puede tomar diferentes roles para llevar a cabo diferentes acciones. Los usuarios pueden ser personas físicas o sistemas.
## 2.Escenarios y casos de uso
Un escenario es una descripción detallada, en lenguaje natural, de la secuencia de pasos que sigue un actor con el sistema para alcanzar un objetivo. No es lo mismo que un caso de uso.
$\space$
### 2.1.Casos de uso
Un caso de uso es una actividad que un actor puede llevar a cabo con el sistema para obtener un resultado. Engloba uno o más escenarios.

Los casos de uso y los escenarios son las formas de reproducir como los usuarios utilizan el sistema para realizar tareas. Los casos de uso suelen ayudar a contemplar escenarios que pueden pasar desapercibidos.
$\space$
#### 2.1.1.Utilidades
Permiten:
+ Obtener fácilmente requisitos.
+ Crear tests.
+ Elaborar manuales de usuario y documentación.
$\space$
#### 2.1.2.Identificación
Para identificar los casos de uso primero se deben identificar a los actores. Una vez se listan, se pueden enumerar las funcionalidades que ofrece el sistema y definir las interacciones con los actores.

Después, para ver los escenarios, se puede partir de un escenario general e identificar el resto, viendo que actores están involucrados en cada uno.

Además se deben identificar los eventos externos a los que tiene que responder el sistema y relacionarlos con los actores y casos de uso específicos. Para ello se usa el diagrama de contexto.
$\space$
#### 2.1.3.Definición
Los casos de uso contienen:
+ Un nombre breve y descriptivo.
+ Una descripción breve.
+ Una condición de inicio del caso de uso.
+ Precondiciones, que son requisitos que se deben cumplir antes de que el sistema lance el caso de uso.
+ Postcondiciones, que son el estado del sistema tras la ejecución del caso de uso.
+ Una secuencia de pasos que muestra las interacciones entre el actor y el sistema. Puede ser el flujo normal, el escenario del que se parte, o flujos alternativos.
+ Excepciones.
$\space$
#### 2.1.4.Validación
Los casos de uso se pueden validar mediante:
+ Pruebas de aceptación.
+ Representaciones, como diagramas de estados.
+ Revisiones con el cliente.
+ Mockups o prototipos.
$\space$
#### 2.1.5.Problemas
Deben evitarse:
+ [c] Demasiados casos de uso.
+ [c] Casos de uso muy complejos.
+ [c] Casos de uso que incluyen decisiones de diseño.
+ [c] Casos de uso que los usuarios no entiendan.


