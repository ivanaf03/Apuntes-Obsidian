[[Tema 6-eXtreme Programming]]

## Qué son las prácticas corolario?
Son prácticas que se apoyan en las prácticas principales y ayudan a mejorar el funcionamiento de XP. Para que funcionen deben estar implementadas las prácticas principales.

Estas se deben revisar y adaptar al contexto y a las principales. Antes de aplicarlas hay que asegurarse que el equipo es suficientemente maduro.

### Cliente real involucrado
Los clientes pasan a formar parte del equipo. Pueden participar en las reuniones semanales o trimestrales. El objetivo de esto es reducir el esfuerzo conectando a quienes tienen necesidades con los que pueden satisfacerlas. Un equipo con el cliente se denomina en XP como equipo completo.

Se puede pensar que esta práctica es mala porque esto hace que el sistema se adapte demasiado al cliente, sin tener en cuenta que este no sirva para nadie más. Esto no ocurre si se piensa en generalización, se adapta el sistema para ser reutilizado (o alguno de sus módulos) en el futuro y si no se adapta todo exclusivamente a ese cliente. El sistema debe ser diseñado de forma modular y flexible y se debe considerar la escalabilidad desde el principio.

Para que el cliente tenga confianza y conozca cómo se desarrolla, hay que ser transparente con él. Esto aumenta la productividad.

### Despliegue incremental
Al sustituir un sistema legacy, se debe hacer de forma gradual. Es muy arriesgado intentar cambiarlo con rapidez. Lo mismo ocurre con los grandes despliegues. 

Para afrontar esto, se deben hacer despliegues incrementales. Para hacerlo se identifican funcionalidades pequeñas y se despliegan en paralelo al sistema real. Para hacer esto se pueden separar y combinar archivos o se entrenan personas específicas para manejar a la vez ambos sistemas. Esto supone un coste adicional, pero es muy seguro ante los riesgos de los despliegues.

En sustituciones de sistemas legacy, esto facilita la adopción progresiva de los usuarios. Además, genera retroalimentación rápida y permite mantener el sistema antiguo mientras el nuevo madura.

### Continuidad del equipo
Los equipos eficaces deben mantenerse juntos. El problema viene en organizaciones grandes, donde se mueven los trabajadores entre equipos mucho más. Se consideran recursos de programación a los trabajadores. Esto genera una falsa micro-eficiencia, ya que sí es correcto matemática o financieramente, pero se ignoran las dinámicas humanas.

Esto genera:
+ Necesidad de adaptación.
+ Pérdida de contexto.
+ Desmotivación.

### Reducción de equipos
Los equipos más maduros pueden reducir su tamaño y seguir siendo igual de competentes. Esto puede liberar personas y formar nuevos equipos, lo que genera más valor en la organización. 

> [!abstract] Definición de Toyota Production System
> El Toyota Production System (TPS) es una idea que, aplicada al software, se basa en evitar repartir la carga de forma equitativa entre todo el equipo para tener siempre recursos disponibles.

### Análisis de causas raíz
Al encontrar un defecto, hay que eliminar el defecto y la causa. El objetivo, además de eliminar el problema, es no cometer de nuevo ese error en el futuro. 

Para responder a un defecto se pueden seguir estos pasos:
1. Escribir una prueba automatizada a nivel de sistema.
2. Escribir una prueba unitaria sobre el defecto.
3. Corregir el sistema.
4. Investigar las causas del error.

Para encontrar las causas de puede recurrir a la técnica de los 5 por qué. Se basa en preguntarse varias veces cuál fue la causa del error.

Conocer las causas del error aporta prevención de riesgos, mejora continua, aprendizaje colectivo, reducción de costes y confianza con el cliente.

### Código compartido
Cualquier miembro del equipo puede mejorar cualquier parte del sistema en cualquier momento. El problema es que es necesario un equipo maduro, donde exista la responsabilidad compartida. Para que esto se de son clave el pair programming y la integración continua.

### Código y pruebas permanentes
El código y las pruebas deben ser artefactos permanentes. Son los únicos artefactos que aportan valor real al cliente. Para hacer buen código y pruebas nos podemos apoyar en el diseño incremental y en las características de los ciclos trimestrales. 

### Base de código única
Solo debe un único flujo de código. Se puede trabajar en ramas temporales, pero no deben durar más de unas horas. Tener muchas ramas supone un gasto de tiempo y recursos. Esto va ligado con la aparición de muchas líneas base. Debe haber el menor número posible de estas.

### Despliegue diario
Se debe poner el software en producción cada noche. Cada diferencia entre los desarrolladores y producción puede ser un riesgo. El equipo de desarrollo debe estar lo más sincronizado posible con el software en producción. 

Es una práctica corolario porque es necesario tener una tasa de defecto muy baja, tener un entorno totalmente automatizado y confianza plena en todo el equipo.

### Alcance negociado en los contratos
Los contratos deben fijar coste, tiempo y calidad. Además tienen que permitir negociación continua del alcance del sistema. 

Firmar más contratos cortos en lugar de uno completo reduce los riesgos. Si el contrato tiene costos muy altos para peticiones de cambio, puede diseñarse con un alcance reducido fijo y menores costes de cambio.

Los contratos deben definir un mecanismo para alinear los intereses de todo el mundo. 

### Pago por uso
El sistema de pago por uso consiste en cobrar cada vez que el sistema es utilizado. Esto permite obtener información precisa y periódica para guiar las mejoras. 

Normalmente se hacen pagos por release. Esto puede ocasionar que se hagan muchas releases para pretender que el cliente pague más. Un modelo intermedio entre ambos ese¡ el modelo de suscripción.