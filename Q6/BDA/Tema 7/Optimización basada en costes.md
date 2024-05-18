[[Tema 7-Optimización]]
$\space$
## 1.Qué es la optimización basada en costes?
Las operaciones de álgebra relacional se pueden hacer de varias formas. Por ejemplo, un `select` puede usar o no un índice. Según se combinen unas técnicas u otras variará la eficiencia de los planes de ejecución.

La idea es seleccionar los procedimientos de menor nivel para cada operación, generar varios planes de ejecución y obtener el de menor coste. No se examinan todos los planes de ejecución, solo los menos costosos.
$\space$
### 1.1.Factores que influyen en el coste
Afecta al coste:
+ Accesos a disco.
+ Uso de espacio adicional en disco para resultados intermedios.
+ Uso de RAM.
+ Uso de CPU.
+ Coste de comunicación.
$\space$
### 1.2.Datos estadísticos para el cálculo de costes
El catálogo guarda:
+ El número de filas, bloques, longitud de las filas y factor de bloqueo (número de filas por bloque)
+ Las particularidades de las tablas, por ejemplo, si está particionada, es una IOT, etc.
+ Histogramas de frecuencia de valores y número de valores distintos por columna.
+ Altura del índice y número de nodos hoja.
$\space$
## 2.Algoritmos de acceso a datos
El coste aproximado será el número de páginas de disco transferidas a memoria. 
$\space$
### 2.1.Select sin índices
El coste de explorar la tabla al completo es el número de bloques. Siempre se puede aplicar, se beneficia de un factor de bloqueo alto y puede ser secuencial o desordenada.

Si la tabla está ordenada por clave de búsqueda y sin huecos se puede hacer una búsqueda binaria. El coste es logarítmico.

Si la tabla está almacenado en un fichero hash la búsqueda es directa.
$\space$
### 2.2.Select con índices
Para el índice primario de valor clave el coste es la altura+1. Basta con recorrer el árbol y acceder al bloque donde está la tabla.

Para valores no clave el coste es la altura + el coste de encontrar el valor buscando secuencialmente.

Para un rango de valores el coste es similar al del caso anterior. Busca el valor más pequeño del rango y hace una lectura secuencial hasta encontrar el mayor valor.

En los dos casos anteriores, si el índice no fuera agrupado, el coste es la altura -1 + el número de páginas del índice + el número de filas que cumplen el `select`.
$\space$
### 2.3.Ordenación
Si los datos están en memoria el coste es el número de bloques. No estamos teniendo en cuenta el tiempo que se tarda en ordenarlos.

Si están en disco el coste es mínimo el triple del número de bloques. Se lee toda la tabla, se ordena en memoria y se escribe en cada partición. Después hay que leer de nuevo todas las particiones para hacer el merge.

Si se hace a través de índices el coste se calcula de forma similar al select para un rango de valores. Se calcula como la altura - 1 + el barrido secuencial + el número de filas.
$\space$
### 2.4.Join con bucles anidados
La forma más básica es:

```sql
for each row tR in R do
    for each row tS in S do
        if tR θ tS then
            output tR · tS -- Join natural o prodcuto cartesiano
```

Es más eficiente bloque a bloque:

```sql
for each block BR in R do
    for each block BS in S do
        for each row tR in BR do
            for each row tS in BS do
                if tR θ tS then
                    output tR · tS
```
$\space$
#### 2.4.1.Sort merge join
Consiste en ordenar primero las tablas por los atributos que hagan el join. Después se recorren ambas en paralelo generando la salida.

![[sort.png]]

![[merge.png]]
$\space$
#### 2.4.2.Hash join
Se basa en crear una tabla hash en memoria de la tabla externa. Se recorre la tabla interna aplicando la función hash con la tabla.

![[hash join.png]]

Existen alternativas:
+ **Grace hash join:** particiona ambas tablas utilizando una función hash para que quepan en memoria. Utiliza un hash join con lo que tiene en memoria y, finalmente, une los resultados.
  + **Hash join híbrido:** supone que la tabla externa cabe en memoria. Si no cabe, particiona la tabla y se queda en memoria con la máxima cantidad.
$\space$
## 3.Agrupación y eliminación de duplicados
Se hace en dos fases. Primero se ordenan las filas o se crea una tabla hash. El objetivo es que los valores iguales estén juntos. Después se eliminan los duplicados.

![[agrupación.png]]