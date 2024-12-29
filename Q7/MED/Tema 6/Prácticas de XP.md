[[Tema 6-eXtreme Programming]]

## Cómo funcionan las prácticas?
Las prácticas son las cosas que se hacen en el día a día. Dependen de la situación. Si la situación cambia, se deben escoger prácticas diferentes que se adapten a las nuevas condiciones. 

### Diferencias con los principios y valores
Los principios pueden aparecer y desaparecer si cambia el dominio. Los valores nunca cambian, se adaptan a cualquier situación. Las prácticas, en cambio, se deben elegir según la situación.

## Prácticas principales
Las prácticas tienden a trabajar bien en conjunto. Unir diferentes prácticas refuerza el efecto de estas. Para comenzar a utilizar XP se recomienda partir de una serie de prácticas llamadas principales.

### Sentarse juntos
Es necesario tener un espacio abierto para todo el equipo. Además, debe haber espacio propio para cada miembro que respete su intimidad. XP no fomenta el teletrabajo, prefiere aumentar el tiempo que se pasa cara a cara.

### Equipo completo
Para que un equipo se considere completo debe estar formado por gente con todas las habilidades y perspectivas necesarias para que un proyecto tenga éxito. Es necesario el sentimiento de equipo. 

Los equipos no deben superar las 12 o 15 personas. No es bueno alternas personas entre equipos, es mejorar alternar equipo entre proyectos. Para hacer esto se pueden dividir los equipos por especialidades, siempre y cuando sigan siendo multifuncionales para evitar la sobreespecialización. Para alinear los diferentes equipos se pueden asignar líderes a estos.

### Espacio de trabajo informativo
En el espacio de trabajo debe haber información suficiente para que si entra una nueva persona pueda tener una pequeña idea del proyecto en segundos. Una buena forma es con espacios de trabajo con comida o bebida para hablar con el equipo y tableros informativos en las paredes similares a Kanban.

### Trabajo con energía
No funciona quemarse un día si eso baja el rendimiento en los siguientes días de trabajo. Solo se debe trabajar las horas en las que se puede ser productivo. Para el desarrollo software es necesario estar relajado y con la mente despejada. Además, XP promueve no ir al trabajo enfermo.

### Pair programming
El pair programming consiste en que dos personas programen juntos en la misma máquina, dialogando y discutiendo ideas. Si una persona se bloquea, el otro toma la iniciativa. Además, mantienen uno al otro centrados en la tarea. Es recomendable rotar las parejas de vez en cuando.

### Historias de usuario
Las funcionalidades deben ser visibles para el cliente. Una vez se escriben las historias, debe estimarse el esfuerzo necesario para cumplirlas. XP rechaza que los requisitos sean obligatorios, deben ser algo visible para el cliente y modificable en todo momento.

Siempre se deben priorizar las historias que más valor aporten al cliente y evitar el "todo o nada". Si hay requisitos que no aporten valor se pueden dejar para el final o incluso descartar.

La estimación temprana es lo que diferencia las historias de usuario de otras prácticas de Ingeniería de requisitos. Sirve como puente entre los desarrolladores y los interesados del negocio.

Para tomar decisiones hay que contrastar dos perspectivas. La perspectiva técnica conoce cómo de complicado es y la perspectiva comercial conoce cómo de importante es para el cliente o mercado. Una vez que el equipo conoce el coste, es cuando decide que funcionalidades dividir, priorizar, etc. Las decisiones están influenciadas por las restricciones y por el valor para el cliente.

Las historias de usuario deben ser breves y tener una descripción corta y significativa. Es muy efectivo colocarlas en una pared física.

### Ciclo semanal
Al principio de cada semana debe haber una reunión. En ella se revisa el progreso y se comprueba que vaya según lo previsto, los clientes escogen las historias que más valor les aporten para desarrollarlas esta semana y las historias se dividen en tareas y se estima la duración de estas.

Lo primero que se debe hacer es escribir los test que deben funcionar cuando las historias estén completas. El resto se tiempo se usa para completar las historias y que pasen las pruebas. El objetivo es tener un software desplegado a final de semana.

Esto tiene la ventaja de que todo el mundo se enfoca en que todo esté funcionando los viernes. Además, no se pierde el tiempo planificando. Cuanto menos tiempo se pierda en la planificación, más tiempo queda para el desarrollo. 

### Ciclo trimestral
Una vez al trimestre es bueno hacer una reflexión sobre el equipo, el proyecto y el alineamiento con los objetivos globales. También se aprovechan para interactuar con proveedores y clientes. Cada trimestre puede estar dedicado a las historias de una temática concreta.

### Distensión / margen
En los planes debe haber tareas que puedan ser eliminadas si no se llega a tiempo. Siempre se puede entregar más de lo prometido. Cumplir con los compromisos mejora las relaciones con los clientes.

En algunas empresas se hace la Semana Geek. Consiste en dejar el 20% del tiempo a los desarrolladores para trabajar en los proyectos que estos quieran. Se utilizan para explorar nuevas tecnologías o herramientas, para probar ideas, contribuir a otros proyectos, etc.

### Construcción en 10 minutos
La construcción del sistema debe tardar menos de 10 minutos. Si tarda más en construirse y correr las pruebas, la gente tiende a hacerlo con menos frecuencia.

### Integración continua
La programación en equipo es un problema de divide, vence e integra. La integración debe ser sencilla y no debe suponer mucho tiempo. Normalmente, se hace de forma asíncrona. Cuando alguien termina una tarea, hace un commit, lo prueba y lo sube o notifica los problemas. Sin embargo, es más sencillo hacerlo de forma síncrona.

Algunas estrategias son:
+ **Integración en ramas específicas:** las funcionalidades se hacen en ramas separadas llamadas feature branches. La integración ocurre al fusionarlas en la rama principal de desarrollo. Esto reduce conflictos y permite trabajar sin afectar a la rama principal.
+ **Integración en momentos específicos:** se establecen horarios para integrar los cambios. Esto facilita la integración en equipos muy grandes.
+ **Integración síncrona:** todos los miembros integran y prueban a tiempo real. Esto evita conflictos y hace que todo el mundo trabaje en la versión más reciente.
+ **Automatización de integración:** se utilizan herramientas como Jenkins, GitLab CI/CD o GitHub actions para ejecutar pipelines automáticamente.

### TDD
Al escribir pruebas antes de hacer el código se mantiene el foco en el alcance que debe tener el desarrollo. Además da pistas sobre el diseño: si una prueba es muy complicada de hacer, quizás el problema es el diseño de la funcionalidad. También aporta confianza y mantiene un ritmo constante de desarrollo.

### Diseño incremental
Se debe revisar el diseño a diario. Un buen diseño debe cumplir las necesidades del sistema todos los días. Esto permite que cambiar el software sea más sencillo.