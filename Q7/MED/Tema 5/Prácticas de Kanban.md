[[Tema 5-Kanban]]

## Limitar el WIP
Limitar el WIP consiste en evitar los excesos de multitareas, ya que esto podría generar sobrecargas en la cadena de proceso en el futuro. Se hace entre todos los implicados en el proyecto. 

### Límite óptimo
Se suele hablar de que el límite óptimo es $2*numPersonas - 1$. La fórmula se basa en la eficiencia del flujo de trabajo, el tiempo de espera mínimo entre tareas y reducir el cambio de contexto. Sin embargo, aunque pueda ser buen valor de partida, debe ser evaluado y ajustado periódicamente para adaptarse a la capacidad real del equipo.

### WIP y rendimiento
Es muy fácil entender como afecta el WIP al rendimiento. Por ejemplo, si una persona trabaja en 4 proyectos a la vez, los proyectos van a retrasarse más que si se limita a solo dos proyectos a la vez:

![[limite_wip.png]]

Esto ocurre porque los proyectos tienen dependencias entre ellos. Además, estar continuamente cambiando de contexto afecta a la productividad de los desarrolladores. 

Otro factor que reduce el rendimiento es llenar de trabajo las esperas. En lugar de realizar otros trabajos durante las esperas, es mucho más productivo aprovechar ese tiempo para buscar los cuellos de botella y resolverlos.

## Visualizar
Para visualizar el trabajo se utilizan elementos como historias de usuario y tareas. Estas se representan en un tablero Kanban que permite ver al equipo el progreso de las tareas a tiempo real. Este tablero además facilita la comunicación y las reuniones y hace visible el flujo de trabajo. También facilita la toma de métricas.

Para que funcionen bien, deben establecerse políticas para diferenciar bien cuando una tarea pasa de una fase a otra. Algo cómodo es poner de colores diferentes las tareas según su tipo (soporte, bugs, features...). Se pueden incluso añadir columnas de buffer, donde se colocan las tareas que están a la espera de pasar de fase. Deben ser siempre lo más simples y visibles posible.

### Tablero Kanban

![[kanban_board.png]]

El tablero está formado por:
+ **Columnas:** son las diferentes etapas del desarrollo y las fases en las que puede estar cada tarea.
+ **Tarjetas:** representan las tareas e historias de usuario.
+ **Columna pri:** columna donde se colocan las tareas prioritarias.
+ **Límites:** la sección de desarrollo tiene un límite de 5 taras y la de test de 3.

### Prioridad en el tablero
Para priorizar y categorizar las tareas se usan las llamadas clases de servicio:
+ **Urgente o expedite:** son tareas que se tienen que priorizar por encima de todas las otras. Se colocan en una fila especial conocida como fast lane.
+ **Estándar:** son tareas que siguen el flujo normal del proyecto.
+ **Fecha objetivo:** son tareas que tienen que estar acabadas antes de una fecha concreta.

Los bugs deben priorizarse antes de que se acumulen y degraden el software. 

### Lead time
> [!abstract] Definición de lead time
> El lead time o el tiempo de entrega es el tiempo que tarda una funcionalidad en pasar por todo el tablero Kanban.

Aunque en Kanban no se hagan iteraciones, sí se deben hacer predicciones para cada historia de usuario. Para ello es clave basarse en el lead time de las tareas.

### Tablero adaptado a Scrum
Se puede adaptar un tablero Kanban a la metodología Scrum. Por ejemplo:

![[tablero_kanban_scrum.png]]

Al finalizar cada sprint se suele hacer una Sprint review. Se puede utilizar la columna "Done" para evaluar el trabajo hecho. Además, para gestionar las diferentes releases se pueden utilizar varios tableros Kanban que se pueden unir, por ejemplo, uno para las épicas que contenga los sprints, donde cada uno de ellos es un tablero.

![[epicas_scrum_kanban.png]]

### Tablero adaptado a equipos de soporte
Los equipos de soporte suelen tener flujos de trabajo muy dinámicos por la llegada y resolución rápida y continua de tareas. Es útil diferenciar las tareas internas de las tareas de los clientes externos. Para ello es habitual el uso de swimlanes. 

> [!abstract] Definición de swinlane
> Las swimlanes son divisiones horizontales de los tableron Kanban que ayudan a separar las tareas según criterios específicos.

Estos tableros se suelen dividir en dos:
+ **First-level support:** se encarga de resolver problemas básicos de los clientes.
+ **Second-level support:** se encarga de las tareas más importantes y complejas, que deben ser resueltas por miembros con mucho conocimiento del producto o servicio.

### Tablero adaptado a equipos de QA
Los equipos de QA están muy vinculados a los equipos de desarrollo. En los tableros Kanban de QA también se suelen usar swimlanes para priorizar tareas. 

![[kanban_tablero_QA.png]]

## Gestionar el flujo
Para gestionar el flujo en Kanban se suele utilizar el diagrama de flujo acumulativo (CFD). Recoge las 3 métricas más importantes del desarrollo ágil:
+ Cycle time
+ Throughput
+ WIP

El objetivo del CFD es mostrar como de estable es el flujo y detectar áreas donde se necesitan refuerzos.

![[Imágenes/CFD.png]]

El eje horizontal representa el marco temporal del proyecto y el eje vertical el número de tarjetas acumuladas. Las bandas de colores son las diferentes etapas del tablero Kanban.

### Interpretación
Si una línea del CFD se vuelve horizontal, significa que no hay tareas entrando en esa etapa durante ese tiempo. Se puede estimar el cycle time trazando una horizontal desde la línea superior de la primera etapa hasta la línea superior de la última etapa.

![[CFD 1.png]]

Si todas las bandas avanzan de forma paralela estaremos en la situación ideal. Es el flujo de trabajo más estable posible. En cambio, si una banda se estrecha progresivamente, es que el rendimiento en esa etapa es mayor al de las otras. Si esto ocurre, se debe ajustar la asignación de recursos para un mayor equilibrio. Si una banda se va ensanchando progresivamente, ocurre lo contrario y se debe corregir el WIP y priorizar las tareas actuales antes de añadir nuevas tareas.

Las bandas siempre son ascendentes, no tiene sentido que una tarea desaparezca del flujo.

## Explicitar las políticas
Se deben definir políticas que sean claras, visibles y entendidas por todo el equipo. Estas ayudan a alinear a todos los equipos. Algunas importantes son:
+ **Definition of done:** indican cuando una tarea o historia de usuario está terminada.
+ **Clases de servicios:** indican la prioridad del trabajo. Se basa en la urgencia, el valor para el cliente y la deuda técnica.
+ **Service Level Agreements (SLA):** indican que tiempos se destinan a cada tipo de trabajo.

## Introducir retroalimentación y mejora colaborativa
La retroalimentación y la mejora continua son dos prácticas de Kanban que se enfocan en:
+ Establecer un ritmo y cadencia regulares para que las entregas sean predecibles.
+ Realizar reuniones.
+ Reflexionar mediante las retrospectivas.

### Day standups
Son reuniones diarias breves para revisar el flujo de trabajo. Funcionan de forma similar a las Daily meetings de Scrum. Permiten identificar bloqueos, evaluar el progreso y buscar mejoras inmediatas. 

### Retrospectivas
Son reuniones que se hacen tras las entregas similares a las Sprint retrospectives. Se analiza qué salió bien, qué se puede mejorar y que se va a hacer en el próximo ciclo. Se suelen usar técnicas como la estrella de mar y métricas del flujo para que el análisis sea lo más preciso posible.