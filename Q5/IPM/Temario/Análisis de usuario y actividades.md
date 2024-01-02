[[Interfaces Persoa Máquina]]

## Enfoques de diseño

### UCD
El UCD (User-Centered Design) es un enfoque de diseño que pone al usuario en el centro del proceso de diseño. Este enfoque se centra en comprender las necesidades, deseos y características del usuario final durante todas las etapas del ciclo de vida del diseño, desde la concepción hasta la implementación y más allá.

Este enfoque tiene ciertos problemas:
+ Muchas aplicaciones tienen distintos tipos de usuarios. 
+ A menudo, los desarrolladores y los usuarios pueden estar separados de manera sistemática.
+ Los equipos de soporte técnico a veces actúan como intermediarios entre los desarrolladores y los usuarios. Esto puede resultar en una barrera de comunicación.
+ Los equipos de ventas y marketing pueden estar más cercanos a los usuarios finales, pero a veces pueden no transmitir de manera efectiva las necesidades y expectativas de los usuarios a los desarrolladores.
+ En algunos casos, ciertos grupos de usuarios pueden ser particularmente difíciles de alcanzar o involucrar en el proceso de diseño. Por ejemplo, directivos y profesionales especializados como médicos.
+ A veces los usuarios no saben con certeza lo que desean.
+ No podemos percibir a la perfección como los usuarios usarán un producto.

Se utilizan técnicas para averiguar lo que hacen los usuarios:
+ **Job shadowing:** consiste en visitar a los usuarios en su entorno y poder extraer directamente información útil.
+ **Contextual interviews:** tras el proceso de observación, es conveniente pasar un tiempo con el usuario preguntándole sobre aspectos observados y otros aspectos que quizás no lo fueron. Se deben evitar opiniones personales y forzar al usuario a realizar el diseño. 
+ **Remote shadowing:** consiste en observar las interacciones de un usuario con un producto, servicio o sistema a distancia. La idea es simular la experiencia de acompañamiento que podría ocurrir de manera presencial, pero utilizando tecnologías para permitir la observación remota. Un ventaja de esto es que podemos revisar las grabaciones. 

Una persona es una representación ficticia de usuarios que encapsula las características y necesidades clave de ciertos grupos objetivo. Sirven para comprender y comunicar de manera efectiva quiénes son los usuarios y cómo interactúan con un producto, servicio o sistema. La representación en personas ayuda a identificar categorías de usuarios y a centrar el producto.

Las desventajas de esto es que son representaciones imaginarias. Además sigue siendo necesario estar en contacto con los usuarios en todas las etapas del desarrollo. Es muy lento hacerlo bien, por tanto no se usa en equipo de trabajo pequeños.

Para crear personas lo primero es catalogar todas las categorías posibles de usuarios e ir agrupándolas lo máximo posible. Suelen bastar 3 o 4 grupos. Se añaden a cada grupo detalles relevantes como el nivel de habilidad, la edad, la experiencia, la importancia, los dispositivos en los que trabaja... 

![[persona.png]]

### ACD
El TCD o ACD (Task-Centered Design) es otro enfoque de diseño que se centra específicamente en las tareas que los usuarios deben realizar con un producto o sistema. Se centra más estrechamente en las actividades específicas que los usuarios llevan a cabo. Es más frecuente que el UCD, ya que es más adecuado para productos orientados a una audiencia general.

Se basa en identificar tareas individuales que el programa debe hacer. Cada tarea es un objetivo. A menudo es conveniente empezar con unos objetivos globales y posteriormente refinarlos en subobjetivos. En un enfoque más cercano a la ingeniería de software.

Se parte de precondiciones, que son tareas que condicionan la tarea actual o información que depende del usuario. Para analizar las tareas antes debemos:
+ Comprobar donde se realizan.
+ Frecuencia de las tareas.
+ Restricciones temporales.
+ Aprendizaje de la tarea.
+ Posibles riesgos.
+ Involucrados en la tarea.

## Card sorting
Las actividades y las necesidades de los usuarios se agrupan en jerarquías. Los efectos invocados en un nivel solo afectan a niveles inferiores. Para el usuario es muy cómodo tener los elementos agrupados.

La jerarquía debe ser superficial para llegar a la información deseada más rápidamente con menos clics, mejorar la accesibilidad a la información y minimizar el número de opciones para evitar abrumar al usuario. Cuando las cantidades de información son demasiado grandes se suelen usar jerarquías profundas.

El Card Sorting es una técnica de investigación de usuarios que se utiliza en el diseño de la información y la arquitectura de la información. Los participantes organizan conceptos, elementos o funciones representados por tarjetas en grupos o categorías según su propia lógica y percepción. Para hacerlo:
1. Se crean tarjetas, ya sea físicas o virtuales, que representan elementos individuales del producto o sistema. Estos elementos pueden ser páginas web, funciones, características, términos, o cualquier otro componente relevante. 
2. Se reclutan participantes representativos del público objetivo. Estos participantes son generalmente usuarios reales o potenciales del producto o servicio que se está diseñando.
3. Se le proporciona a cada participante un conjunto de tarjetas y se les pide que organicen esas tarjetas en grupos o categorías que tengan sentido para ellos. Los participantes también pueden etiquetar cada grupo con un nombre que refleje el contenido o propósito común de las tarjetas en ese grupo.
4. Se recopilan los datos resultantes de las sesiones de Card Sorting. Esto implica analizar cómo los participantes han agrupado y etiquetado las tarjetas. Los resultados proporcionan información sobre la estructura mental que los usuarios tienen respecto a la información o funciones del producto.

Existen dos tipos principales de Card Sorting:
+ **Abierto:** los participantes crean sus propias categorías y las etiquetan.
+ **Cerrado:** se proporcionan categorías predefinidas, y los participantes deben asignar las tarjetas a esas categorías.

## Modelo mental
Un usuario tiene ideas preconcebidas de cómo deben funcionar ciertas cosas. El concepto que el usuario se forma de cómo funciona algo se llama modelo mental.

Los productos generalmente siguen 3 modelos:
+ **Modelo mental:** como el usuario cree que el sistema funciona.
+ **Modelo de diseño o IU:** como se presenta el producto al usuario.
+ **Modelo de implementación:** como se implementa al producto.

En un producto ideal, los tres modelos son consistentes. El interfaz representa perfectamente la implementación y el usuario entiende perfectamente lo que ve. Aunque realmente no suelen ser consistentes. 

Los principios para ayudar al usuario a seguir modelos mentales son:
+ Simplicidad
+ Familiaridad
+ Reconocimiento
+ Flexibilidad
+ Feedback
+ Seguridad
+ Affordances (potencial, adecuación)