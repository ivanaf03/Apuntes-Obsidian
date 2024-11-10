[[Tema 4-Scrum]]

## Qué es el Timeboxing en Scrum?
En Scrum se dividen las tareas con una asignación de tiempo limitada y definida. Esto facilita la priorización de tareas y delimitación de marcos de tiempo fijo, los Sprints.

### Ley de Parkinson
La ley de Parkinson dice que el trabajo suele durar lo que dure el tiempo que se tiene para realizarlo. Al fijar plazos cortos se reduce la posibilidad de procrastinación y se evita posponer tareas. Esto incrementa un montón la eficiencia.

### Ventajas
Trabajar con Timeboxing y Sprints permite:
+ Definir objetivos claros.
+ Evitar distracciones.
+ Tener retroalimentación constante.

## Gráfico de avance o burn-down
El burn-down es un gráfico que se actualiza en las reuniones de seguimiento del sprint para monitorizar el ritmo del avance y detectar las desviaciones lo antes posible. Mide el esfuerzo pendiente a lo largo del Sprint.

En el eje x se ponen los días del Sprint y en el eje y el trabajo que falta por realizar.

![[burndown.png]]

### Project burn-down chart
El project burn-down chart es un gráfico burndown para todo el proyecto. El eje x representa los Sprints y el eje y representa el trabajo total restante.

## Gráfico burn-up
El gráfico burn-up es una representación que muestra el progreso del producto de forma positiva, tal que refleja lo que está hecho en lugar de lo que queda por hacer. 

En el eje x se representa el tiempo en Sprints y en el eje y la cantidad de trabajo completado en relación al total del proyecto.

![[burnup.png]]

## Velocidad
La velocidad en Scrum se mide como la cantidad de trabajo realizada en un Sprint o en un tiempo predeterminado. Se suele medir como la suma de puntos de historia completados. Sirve para predecir la capacidad de trabajo del equipo y aprovecharla para planificar Sprints futuros.

$$Velocidad = \frac{trabajo \space completado}{tiempo \space empleado}$$

### Métodos de avance
Para que la velocidad sea constante se utilizan dos tácticas:
+ **Incremento iterativo:** usar Sprints iterativos ayuda a mantener el ritmo.
+ **Incremento continuo:** se trabaja de forma continua, sin paros ni puntos con esfuerzo excesivo.

### Tiempos
Existen dos conceptos de tiempo:
+ **Tiempo real:** es el tiempo de trabajo, la jornada laboral. Se utiliza para generar los puntos de historia. Estos también dependen de otros factores, como la experiencia, la similitud a otras tareas, etc.
+ **Tiempo ideal:** es el tiempo de trabajo en condiciones ideales, suponiendo que no ocurren interrupciones. No se utiliza como unidad de medida. Se usa para estimar el esfuerzo necesario para realizar una tarea.

## Trabajo
Medir el trabajo es necesario para registrar el trabajo ya realizado y poder estimar el que queda por hacer. Medir el trabajo realizado es muy sencillo y se hace con puntos de historia. 

El trabajo necesario para completar una historia de usuario no se puede prever de forma exacta, ya que las funcionalidades se pueden resolver de muchas formas. Al existir tanta incertidumbre, se trabaja con estimaciones basadas en el conocimiento del equipo.

### Unidades de medida del trabajo
Para medir el trabajo se puede medir el producto que se tiene que construir. Una forma es mediante los puntos función de COCOMO (Constructive Cost Model). Es un modelo matemático utilizado para estimar los costes del software. 

Para estimar las líneas de código para medir el esfuerzo se utilizan los puntos función. Para calcularlos se tiene en cuenta el número de:
+ Entradas de usuario
+ Salidas para el usuario
+ Consultas del usuario
+ Ficheros
+ Interfaces externas

La fórmula con la que se calculan los puntos función es:
$$FP = \text{conteototal} \times \left( 0.65 + 0.01 \times \sum_{i} F_i \right)
$$

Los $F_i$ son valores del 0 al 5 en función de ciertas preguntas sobre el sistema. Una vez calculados, para obtener el número de líneas de código se aplica un factor en función del lenguaje de programación.

## Cálculo de puntos de historia
Los puntos de historia se utilizan para estimar el esfuerzo necesario para completar una tarea o historia de usuario. Sirven para ver el trabajo relativo entre distintas tareas. 

Para calcularlos se puede partir de una tarea sencilla y asignarle 1 punto de historia. El resto de tareas se comparan con ella. Por ejemplo, si iniciar sesión tiene 1 punto de historia, realizar un mercado de jugadores de una liga tendría 3 puntos de historia aproximadamente.

La definición de los puntos de historia tiene que ser consistente dentro de la organización. Además, las estimaciones deben revisarse constantemente para cambiarlas según el rendimiento del equipo.

### Planning Poker
Es una técnica que se utiliza para conseguir una estimación del esfuerzo de cada tarea. Se utilizan tarjetas con los números de la sucesión de Fibonacci que se dan a cada participante. Además se usa una lista de características en base a las historias de usuario.

Un moderador preside la reunión y va diciendo las tareas. El desarrollador con más conocimiento de la tarea la explica y se debate entre todos. El gestor del proyecto se encarga de registrar la discusión. Luego, cada desarrollador coloca una tarjeta boca abajo con su estimación. 

Se muestran las tarjetas de forma simultánea. Las personas con las estimaciones más altas y más bajas justifican su estimación y se repite el proceso hasta obtener un consenso. 