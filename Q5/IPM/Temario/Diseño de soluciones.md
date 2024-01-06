[[Interfaces Persoa Máquina]]

## Prototipado
Los prototipos que se hacen a papel son representaciones muy sencillas y rápidas de corregir y modificar. Para diseñar la estructura usamos:
+ Diagramas de flujo
+ Storyboards

Una vez determinada la estructura se pueden hacer bocetos de las pantallas. El diseño de la estructura nos permite saber ya qué funcionalidades y elementos son necesarios en cada pantalla. Para ello usamos:
+ Wireframes
+ Mockups

### Diagramas de flujo
Es preferible hacer diagramas de flujo sencillos que cubran todas las necesidades del usuario. Por ejemplo:
![[diagrama flujo interfaz.png]]

### Storyboards
Es una técnica originalmente desarrollada para planificar animaciones en películas. Desenvuelven el camino de un usuario para una cierta acción en una serie de snapshots. Se centra en las interacciones.

Solo es recomendable en acciones difíciles de diseñar.

### Wireframes
Representan la estructura exacta de una pantalla sin detalles de decoración. Se centran en el contenido que se quiere mostrar no en la apariencia de este. 
![[wireframe.png]]

### Mock-ups
Los mock-ups son wireframes decorados. Añaden detalles como sombras, imágenes... Sirven para dar pistas o facilitar al usuario el acceso a funcionalidades.

## Testeo de prototipos
Cuando los problemas no son obvios en el prototipo podemos asumir que nuestros prototipos son versiones primitivas del producto y se pueden realizar test de usabilidad.

Primero se hacen los guerrilla test. Se muestran los bocetos a varios usuarios las funcionalidades.

Podemos hacer tests más complejos pidiendo al usuario que realice una determinada tarea sobre los prototipos. Es recomendable que los usuarios no estén familiarizados con el entorno de trabajo.

No debemos ayudar al usuario en ningún momento en el test. Así veremos si es, por ejemplo, lo suficiente intuitivo. Después se analizan los resultados de forma cualitativa para buscar los problemas y refinarlos.

## Realismo
En general, los interfaces se diseñan para tener una apariencia realista. Esto ayuda a que el usuario reconozca ciertas funciones. Sin embargo, si es excesivamente realista puede crear confusión.

En general es buena idea usar símbolos para representar elementos funcionales del interfaz.

El skeuomorfismo en diseño de interfaces se refiere a la práctica de utilizar elementos de diseño que imitan la apariencia de objetos del mundo real. No es buena práctica, ya que puede limitar las funcionalidades.

![[realismo.png]]

## Interacción natural
Existen varios paradigmas de diseño de interfaces:
+ Command line interface
+ Graphical user interface
+ Natural user interface

El paradigma NUI puede resultar muy cómodo para el usuario pero es el más complicado de perfeccionar. La idea principal detrás de una NUI es que la interfaz debería adaptarse más a las acciones y comportamientos naturales de los usuarios, como gestos, voz, movimientos corporales o incluso la escritura a mano, en lugar de depender principalmente de dispositivos periféricos tradicionales como el teclado y el ratón.

Aspectos a considerar en un NUI: 
+ Dar feedback de la manera más inmediata posible respecto de las acciones del usuario.
+ Cuando tenga sentido usar gestos que activen comandos, no que manipulen objetos en la pantalla.
+ Evitar el aprendizaje de gestos demasiado complejos.
+ Controlar entradas accidentales.

## Ley de Fitts
[Ley de Fitts en UI bien explicada](https://arkana.io/2023/11/15/ley-fitts-que-es-ejemplos/#:~:text=Al%20diseñar%20interfaces%2C%20la%20Ley,así%20la%20usabilidad%20y%20eficiencia)

$$
MT = a + b \cdot \log_2\left(\frac{D}{W} + 1\right)
$$
$$
\begin{align*}
MT & : \text{Tiempo de movimiento requerido} \\
D & : \text{Distancia al objetivo} \\
W & : \text{Tamaño del objetivo} \\
a, b & : \text{:Tiempo de arranque/parada y factor inverso a la velocidad de movimiento}
\end{align*}
$$

La Ley de Fitts es un principio en el diseño de interfaces que describe la relación entre el tiempo de movimiento hacia un objetivo, la distancia al objetivo y el tamaño del objetivo.

Se aplica:
+ Ubicar elementos importantes o frecuentemente utilizados en los extremos de la pantalla (si no es táctil) virtualmente les otorga un tamaño infinito, reduciendo así el tiempo de movimiento necesario. 
+ La adopción de menús radiales de contexto optimiza la disposición de opciones alrededor de un punto central, disminuyendo la distancia media y mejorando la eficiencia de acuerdo con la Ley de Fitts. 
+ Separar elementos pequeños y proporcionar márgenes entre ellos mejora la precisión de la interacción, evitando clics accidentales.
+ Aumentar el tamaño de los elementos objetivo facilita la interacción al reducir el tiempo de movimiento necesario.
+ Mantener elementos "sensibles" o destructivos en un tamaño razonablemente pequeño o alejado ayuda a prevenir acciones no deseadas, al reconocer la necesidad de seleccionar estos elementos con cuidado.

## Interrupciones
En general, las interrupciones deben ser evitadas. A veces las interfaces tienen que tomar decisiones por el usuario. Otras veces se debe preguntar al usuario, por ejemplo, en los instaladores.

Por tanto, solo se debe interrumpir tareas en momentos importantes. Si se abusa de las interrupciones, el usuario no va a leerlas demasiado y se va a equivocar. Es importante dejar al usuario revertir sus acciones.

## Funcionalidades
El crecimiento de funcionalidades sin medida puede desbaratar unos diseños originales bien definidos. Demasiadas funcionalidades puede evitar el acceso de nuevos usuarios; sin embargo, los usuarios experimentados piden más funcionalidades. El usuario va a demandar nueva funcionalidad como solución a problemas.

La regla de los 5 por qué es una técnica utilizada en el análisis de causa y efecto para identificar la raíz de un problema o situación. Esta regla se basa en la idea de realizar preguntas sucesivas, repitiendo la pregunta "¿Por qué?" cinco veces (aunque el número puede variar), con el objetivo de llegar a la causa principal del problema. Se puede usar para ver si esa funcionalidad es necesaria.

En vez de añadir nuevas funcionalidades mejor hacer las antiguas más usables. Otra recomendación es tratar de agrupar varios problemas en una solución.

Las propiedades invisibles son aquellas que mejoran la aplicación y no suponen una carga para el usuario. 

Para eliminar funcionalidades:
+ Investiga datos de uso sobre el programa .
+ Esos datos hay que cogerlos con perspectiva de lo que se esperaba de cada parte de la aplicación en términos de tipo de usuario, frecuencia de uso... 
+ Informar a los usuarios (pero no dejarles decidir).
+ Facilitar alternativas si es posible.

Una característica importante es la facilidad con la que los usuarios son capaces de encontrar y usar una funcionalidad. Para evitar la masificación en pantalla se pueden esconder funcionalidades y que sean activadas por los usurios, por ejemplo, en un menú.

## Animaciones
A veces cambios de estado visuales de la aplicación pueden desorientar al usuario. Animar el cambio de estado (minimizar una ventana por ejemplo) ayuda al usuario a seguir el proceso.

Debemos evitar animaciones innecesarias y ayudar a los usuarios a formar modelos mentales adecuados. Un ejemplo es la flecha del botón de back.

## Consistencia
La consistencia representa la armonía o lógica entre las diferentes partes del producto. Muchas veces la consistencia se usa referida a la apariencia:
+ Los botones en la aplicación no parecen iguales que los que tiene el sistema por defecto.
+ Ventanas diferentes unas de otras.
+ Diferentes formatos de texto.

La consistencia de comportamiento o funcional se basa en que cuanto más se parezca algo a lo que el usuario previamente conoce más fácil es de despertar sentimiento de inconsistencia. El usuario espera que se comporte de la misma manera. 

## Modos
Un modo es una parte de la aplicación de la que hay que entrar/salir y que restringe o acota las operaciones que se pueden llevar a cabo mientras esté activo. Mientras una aplicación (o ventana) esté en un cierto modo, su comportamiento frente a las entradas del usuario varían y afectan a la usabilidad. Un ejemplo es el Caps Lock.

Los modos deben ser obvios. Por ejemplo, el Caps Lock tiene una luz en teclado. Además se puede avisar con un texto en la pantalla. En general se recomienda usar checkboxes o radiobuttons para indicar modos activos.

Los diálogos son un tipo específico de modo. Pueden robar el foco.

Hay veces que los modos son necesarios:
+ Para mostrar funcionalidades sólo cuando son aplicables.
+ Mientras se entre intencionadamente, se vea de forma obvia su presencia y se conozca la manera de abandonarlo no hay problema.

Los quasimodos son modos temporales que solo están activos mientras el usuario explícitamente los mantenga así. Por ejemplo, el shift. Siempre son obvios, esperados y fáciles de abandonar. 

## Velocidad
La velocidad es la característica más importante. A diferencia de otros problemas vistos, en caso de aplicaciones lentas los usuarios pueden abandonarlas rápidamente. 

La capacidad de respuesta (responsiveness) de un sistema es crucial:
+ Acciones que duran < 0.1 s se consideran instantáneas.
+ Acciones < 1 s, aunque no instantáneas, no permiten perder el foco con facilidad al usuario.
+ Por encima de 1s se corre ese riesgo.

Si una operación va a durar más de lo esperado es bueno dar feedback al usuario. Si son pocos segundos podemos usar el reloj de arena o un círculo dando vueltas. En acciones más largas es bueno usar barras de progreso o contadores.

En algunos casos es recomendable también indicarle al usuario en qué tarea se está si la acción incluye unas pocas tareas fácilmente identificables. Por ejemplo, en la copia de ficheros.

Más importante que la velocidad real es la velocidad percibida. Se puede mejorar:
+ Mostrar resultados parciales cuando sea posible.
+ No bloquear la interfaz con operaciones lentas.
+ Decoraciones: efectos de ondas en las barras de progreso en sentido contrario al avance de la misma.