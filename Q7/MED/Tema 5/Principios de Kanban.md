[[Tema 5-Kanban]]

## Comprensión
Se centra en entender lo qué se hace en todo momento y cómo se hace. Esto incluye desde el propio proyecto hasta el enfoque de la organización. Para ello se deben realizar pequeños cambios o adaptaciones según el conocimiento de la situación.

Para entender el flujo de trabajo hay dos enfoques principales:
+ Knowledge Discovery Process.
+ Value Stream Map.

### Knowledge Discovery Process
Consiste en organizar los elementos de trabajo según sus estados y el conocimiento adquirido de ellos. Es útil para saber como evoluciona el conocimiento sobre las tareas y el cliente.

Por ejemplo, se pueden definir estados como "recopilación de requisitos", "desarrollo de módulos", "integración con otras herramientas"..., "retroalimentación del cliente". A medida que el equipo pasa por cada fase para cada una de las tareas, adquiere más conocimiento.

### Value Stream Map
Se utiliza para analizar los flujos materiales e información necesarios para poner a disposición del cliente un producto o servicio. Se crea el mapa y se buscan sobre el las cosas que no aportan valor, como tiempos de espera, movimientos innecesarios, etc. Después se crea un mapa con los desperdicios eliminados y se hace en base a ambos el plan de mejora para pasar del malo al bueno.

> [!abstract] Definición de value chain
> La value chain o cadena de valor es el conjunto de actividades necesarias para transformar un insumo en un producto final que aporte valor.

Gracias a la cadena de valor podemos encontrar cuellos de botella.

Para crear el mapa se mapea el flujo de trabajo de un proyecto concreto. Suelen seguirse estos pasos:
1. Identificar las acciones que se realizan en el proyecto.
2. Especificar el tiempo que lleva realizarlas. Se suele medir en 8 horas por día o 40 por semana.
3. Medir cuanto tiempo fue efectivo y cuanto tiempo se estuvo en espera.
4. Especificar la cantidad de tiempo entre actividades.
5. Identificar y señalar los retrocesos, junto a la probabilidad de que estos ocurran.
6. Sumar todo el tiempo dedicado a trabajar en el proyecto.

![[value_stream_map.png]]

El tiempo total real del proyecto se calcula como la suma de todos los tiempos, sin contar los retrocesos: 
$$0.5+320+8+80+160+320+8+80+100+120+160+2+80+280+80+240+80+8=2206.5$$
El tiempo total del proyecto se calcula como la suma de todos los tiempos contando los retrocesos:
$$2206.5+0.2*(120+160+2)+3*0.65*(280+80+240)=3433$$
El tiempo trabajado se calcula como la suma de los tiempos de trabajo, teniendo en cuenta los retrocesos:
$$0.5+0.1+60+1+40+40+2+80+40+3+0.2*(40+2)+3*0.65*(80+40)=509$$
Con estos dos valores podemos calcular la eficiencia:
$$509/3433=14.9\%$$

Otros tiempos o métricas que se pueden calcular son:
+ **Cycle Time:** es el tiempo total de un proceso o de una actividad concreta, incluyendo esperas.
+ **Lead Time:** es el tiempo desde que un cliente hace una solicitud hasta que la recibe. Abarca todos los procesos y esperas.
+ **Wait Time:** es el tiempo que un elemento pasa esperando, por ejemplo, por aprobaciones o disponibilidad de recursos.
+ **Processing Time:** es el tiempo efectivo realizado sobre un elemento, sin incluir esperas.
+ **Throughput:** es la cantidad de elementos, como tickets, que pasan por el sistema en un periodo de tiempo concreto.

### DevOps
Las prácticas de DevOps permiten mejorar los tiempos y la eficiencia de desarrollo mediante la colaboración estrecha entre los equipos de desarrollo (Dev) y operaciones (Ops). Promueven la automatización de procesos, la integración continua (CI) y la entrega continua (CD), lo que facilita el despliegue rápido y frecuente de aplicaciones. Además, fomenta la monitorización constante y la retroalimentación continua, lo que mejora la calidad del software y permite detectar y corregir errores de manera más rápida.

## Acuerdo
Se centra en la puesta de acuerdo para las necesidades de cambios e implementación de mejoras. Para que todo salga bien, deben estar de acuerdo quiénes solicitan el cambio, quiénes entiendes el alcance y el impacto que este pueda tener, quiénes lo implementarán y a quién afectará el cambio.

Para que sea fácil, los grupos de trabajo deben estar superpuestos. El acuerdo es un proceso continuo, no tiene que ver con la jerarquía organizacional, y debe surgir de forma natural.

## Respeto
Se centra en dar el valor que merecen los miembros del equipo. El respeto fomenta la comprensión y ayuda a encontrar soluciones que beneficien a todo el mundo.

## Liderazgo
Se centra en mantener cierto liderazgo en todo el personal de la organización, no solo en los altos cargos. Esto permite a cualquiera ser líder, lo que significa que debe sugerir ideas y sugerencias de mejora, participar en la ejecución de estas y servir de modelo para los demás compañeros.

Kanban fomenta la toma de decisiones descentralizada. Los problemas y soluciones deben ser afrontados por las personas más ligadas a estos. Esto permite una rápida adaptación a cambios.