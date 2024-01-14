[[Tema 2-Gestión y planificación de proyectos]]

## Técnicas de representación
### Diagrama de Gantt
Es una representación en una escala temporal de las actividades mediante barras. Su longitud representa la duración en el calendario. Es una representación simplificada de una red de precedencia.

![[diagrama de Gantt.png]]
Se suelen decorar para ver sus dependencias.

### Red de precedencia
Antes de los años 60 el diagrama de Gantt era la única técnica que se usaba. Entonces comenzaron a utilizarse técnicas que permiten relacionar las actividades de un proyecto. Su objetivo es establecer las dependencias entre las distintas tareas y encadenarlas entre sí.

La red es un grafo dirigido sin ciclos. Sirve para señalar las relaciones de secuencia entre las actividades de un proyecto. Analizar esta red nos permite localizar el camino crítico de la planificación.

Existen 2 técnicas:
+ **PDM (Precedence Diagram Method):** Los nodos representan actividades  y los vectores sus dependencias. Es la técnica más usada. Utiliza las dependencias FF, CC, FC y CF.
+ **ADM (Arrow Diagramming Method):** Los vectores representan actividades  y los nodos sus dependencias. Sus dependencias pueden ser lineales, de convergencia o de divergencia. Existen 3 reglas en un diagrama ADM:
	+ El tamaño del vector no indica la duración de la actividad.
	+ Todas las relaciones son FC.
	+ Los nodos se numeran de forma creciente, es decir, el nombre del nodo tiene que ser mayor que el del anterior (por ejemplo, A--->B).

### Histograma
Es un diagrama de barras que muestra los datos cuantitativos de una misma variable. Se suele usar un histograma de recursos porque muestra el uso de un recurso a lo largo del tiempo. 

Se utilizan para ver si un recurso está sobreasignado en varios proyectos. Cuando esto ocurre hay que ponerse de acuerdo en que proyecto trabaja primero.

Hay que tener cuidado con las sobrecargas ficticias. Por ejemplo, cuando hay dos actividades que duran 4 horas cada una en las que el recurso R1 está trabajando al 100% en ambas. Por asignación si hay sobrecarga, pero realmente no.
![[histograma.png]]

## Técnicas de estructuración
### WBS (Work Breakdown Structure)
Consiste en estructurar las tareas por tipos, niveles, etc. Por ejemplo, primero desglosarlas en fases de un ciclo de vida, cada fase en subfases y así constantemente. El principal problema del desglose es el tiempo entre actividades (a veces existen actividades que necesitan tiempo entre ellas).

### OBS (Organisational Breakdown Structure)
Es una técnica similar a la WBS, pero en lugar de por tareas, por las unidades organizativas. Es interesante porque al mezclar ambas técnicas podemos ver que grupo o recurso trabaja en que actividad.
![[wbs y obs.png]]

## Técnicas de programación
### PERT
Se orienta a la técnica ADM. Permite considerar las probabilidades. Estima la duración de un proyecto partiendo de la secuencia de actividades y de una estimación de su duración. La duración de cada actividad se calcula como una media ponderada de 3 valores:

$(optimista+4*masProbable+pesimista)/6$

Los pasos que sigue esta técnica son:
1. Elaboración de una red de precedencia ADM.
2. Cálculo de tiempos: pesimista (tiempo máximo), optimista (tiempo en el mejor de los casos) y más probable (tiempo normal). Realizar la media ponderada con la fórmula de antes.
3. Cálculo de fechas early y late de comienzo de fin de cada actividad. Con esto se calcula la holgura.
4. Determinación del camino crítico. Un hito y una actividad crítica son aquellos que tienen holgura 0.
5. Definición de fechas más tempranas de inicio y fin.

Cuando se da una situación donde la demora se da en días transcurridos, el camino crítico parece desaparecer, pero en realidad no. Por ejemplo, en una actividad relación FC+2dt que termina en miércoles, si se retrasa 1 día o 2 no pasa nada; pero si se retrasa 3 días, se produce un retraso importante.

### CPM
Se orienta a la técnica PDM. Permite calcular el camino crítico. Con esto se obtienen las fechas mínimas esperadas y las máximas permitidas de las tareas. Se calculan con las duraciones e interdependencias de estas.  

Los pasos que sigue esta técnica son:
1. Elaboración de una red de precedencia PDM.
2. Identificar todos los caminos del grafo de principio a fin del proyecto.
3. Calcular los tiempos de todos los caminos.
4. Identificar el camino crítico, que es el de mayor duración.