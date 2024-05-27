[[Tema 9-Validación de requisitos]]
$\space$
## 1.Tests
Se pueden hacer tests basados en los requisitos del sistema. Hacerlos pronto permite detectar muchos problemas. Una buena forma es siguiendo el ciclo en V. 

En la fase de requisitos se hacen tests conceptuales, no existe un software para probarlo. El testing no siempre lo hacen los desarrolladores. En la validación de requisitos simplemente se comprueba que lo entregado cumple con los requisitos.
$\space$
### 1.1.Ventajas
El testing:
+ [p] Al utilizar herramientas automatizadas se pueden comprobar detalles de bajo nivel.
+ [p] Se pueden repetir las pruebas exhaustivamente.
$\space$
### 1.2.Inconvenientes
El testing:
+ [c] Requiere mucho esfuerzo y tiempo.
+ [c] No se puede probar todo.
+ [c] Muchas especificaciones no son ejecutables.
+ [c] Los tests no confirman la ausencia de errores.
$\space$
### 1.3.Tests de simulación
Cuando se consigue un ejecutable se pueden probar varias entradas para comprobar que salidas producen. Esto lo pueden hacer hasta los clientes. 

Las simulaciones no confirman la ausencia de errores.
$\space$
### 1.4.Model checking
En los sistemas formales se puede aplicar model checking. Consiste en representar la especificación como un grafo de estados dirigido. 

La verificación de modelos consiste en probar todos los estados del sistema posibles a partir de un estado inicial para confirmar que se ajusta a los requisitos. Es una técnica difícil de usar en entornos comunes, como aplicaciones web, proceso de datos, etc.
$\space$
## 2.Reviews
Son revisiones de la especificación. Lo hacen personas que no estén involucradas en la especificación. Lo ideal es que el equipo esté formado por personas que conozcan el dominio y personas que no. 

Se encuentran errores más rápido y en más cantidad. Es la técnica más usada. 
$\space$
### 2.1.Cómo se hace una review?
1. Se leen y analizan los requisitos
2. Se buscan problemas.
3. Se hace una reunión para discutir los problemas.
4. Se ponen de acuerdo en qué hacer para resolverlos.
$\space$
### 2.2.Ventajas
Las reviews:
+ [p] Permiten validar cualquier elemento de la especificación.
+ [p] Se encuentran errores antes que los tests.
+ [p] Ayudan a los desarrolladores a entender el proyecto a más alto nivel.
$\space$
### 2.3.Inconvenientes
Las reviews:
+ [c] Pueden parecer inútiles a veces.
+ [c] Requieren tiempo de preparación.
$\space$
## 3.Técnicas de validación por revisión
Pueden ser:
+ Lecturas del documento
+ Firmas del documento.
+ Revisiones en grupo.
+ Inspecciones de código.
$\space$
### 3.1.Lectura del documento
Los revisores leen el documento para buscar errores o funcionalidades que falten. No lo deben hacer los propios autores. El principal problema es el tiempo que consume.
$\space$
### 3.2.Firmas del documento
La firma del documento consiste en que el revisor de el visto bueno al documento. Permite a los revisores ser parcialmente responsables de los fallos y, con esto, que tengan más cuidado en la revisión. 
$\space$
### 3.3.Walkthroughs
Son revisiones informales a alto nivel. El autor explica a los demás el documento para encontrar errores y compartir el conocimiento. Los demás participantes deben hacer preguntas. 

No requiere participación previa. Son muy útiles en revisiones de documentos. Además del equipo, se puede reunir un grupo de stakeholders para ver los diferentes puntos de vista e intereses. Es muy habitual hacerlo en metodologías ágiles.
$\space$
### 3.4.Inspecciones formales
Son trabajos en grupo con procesos de revisión dirigidos, estructurados y con roles asignados. Es la forma más precisa para llegar a cero errores. Suelen participar:
+ Autor
+ Revisores
+ Moderador
$\space$
#### 3.4.1.Reunión
La reunión suele ir precedida de un walkthrough. Los revisores reciben los requisitos y los leen y documentan los fallos. El objetivo de la reunión es encontrar errores.

No se proponen soluciones a los errores. El autor es el encargado de solucionarlos después de la reunión. Uno de los trabajos del moderador es evitar esto. 

Las reuniones deben estar limitadas en tiempo, como mucho 1 hora. Una vez acabada la reunión, se considera acabada la inspección cuando los errores han sido corregidos.
$\space$
### 3.5.Inspecciones dirigidas
Son una variante de las inspecciones formales. El líder designa roles concretos a cada revisor para que no tengan que ver todo el documento.
$\space$
### 3.6.Revisiones activas
Consisten en preguntas del autor a los revisores que solo se pueden responder mediante el documento. Obliga a los revisores a leer el documento y ayuda a encontrar fallos si no se pueden contestar ciertas preguntas.
$\space$
### 3.7.Inspecciones del código
Son una alternativa a los test. Permiten a los desarrolladores ser más prudentes. A veces una revisión de otra persona ayuda a ver errores.
$\space$
#### 2.7.1.Ventajas
Permiten:
+ [p] Implementar estándares de codificación.
+ [p] Aprender mediante entender y explicar.
$\space$
#### 2.7.2.Desventajas
Los problemas son:
+ [c] Una personalidad fuerte puede dar puntos de vista incorrectos.
+ [c] Mucha gente discute.
+ [c] Lleva tiempo.
+ [c] Hay gente con opiniones muy concretas sobre la codificación.
