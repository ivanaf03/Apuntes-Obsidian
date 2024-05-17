[[Tema 6-Diseño físico]]
$\space$
## 1.Particionado de tablas e índices
Particionar consiste en fragmentar una tabla o un índice en partes más pequeñas para que sean más manejables. No se parten filas completas o entradas de índices. Cada partición se llama segmento.

Cada partición puede estar en un tablespace diferente. Una vez toda la taba esté particionada se pueden añadir o borrar particiones.

![[partición oracle.png]]
$\space$
### 1.1.Tipos de particionado de tablas
Puede ser:
+ **Basado en rangos:** los datos se separan en base a rangos de valores. Sirve en dominios de datos continuos, como fechas.
+ **Basado en listas:** se definen listas de valores para cada partición. Sirve para dominios de valores discretos.
+ **Hash:** se aplica una función hash a la clave de particionado. 
+ **Compuesto:** consiste en un particionamiento por rango al que se aplica en cada partición otro particionado.
$\space$
### 1.2.Tipos de particionado de índices
Puede ser:
+ **Local:** van asociados con la partición de la tabla.
+ **Global:** tienen un esquema propio de particionado.
+ **Sin particionar:** van todos en una única partición.

![[index partitions.png]]$\space$
### 1.3.Ejemplos

```sql
-- Particionado por valor
-- VALUES(DEFAULT) en la última partición serviría para "todos los demás valores"
create table emp_part_list (
empno number(4,0),
deptno number(2,0), ...
) partition by list (deptno) (
partition emp_part1 values (10,20),
partition emp_part2 values (30,40)
);

-- Particionado por rango en hiredate, especificando distinto tablespace para cada partición.
-- Creado un índice con particionado local sobre HIREDATE
create table emp_part_range (
empno number(4,0),
hiredate date, ...
) partition by range (hiredate) (
partition emp_part1 values less than (to_date('01/01/2018','DD/MM/YYYY')) tablespace users,
partition emp_part2 values less than (maxvalue) tablespace users2
);
create index i_emp_part_range_hiredate
on emp_part_range(hiredate) local;

-- Particionado por hash sobre EMPNO, especificando 5 particiones.
create table emp_part_hash (
empno number(4,0), ...
) partition by hash (empno) partitions 4
store in (users, users2, users3, users4);

```
$\space$
### 1.4.Ventajas e inconvenientes
El particionado puede ser útil, pero también tiene inconvenientes.
$\space$
#### 1.4.1.Ventajas
Sus ventajas son:
+ [p] Pueden optimizarse consultas descartando particiones.
+ [p] Aumenta el paralelismo.
+ [p] Aumenta la  disponibilidad.
+ [p] Mejora de las operaciones DML masivas.
+ [p] Agrupa y, a veces, esto implica ordenación.
+ [p] No es necesario reconstruir todo el índice si se borra una partición.
+ [p] Mejoras en tareas de administración. 
$\space$
#### 1.4.2.Inconvenientes
Sus problemas son:
+ [c] Puede empeorar la eficiencia.
$\space$
## 2.Clusters
Un cluster es el almacenamiento de varias tablas en el mismo bloque físico de base de datos. Se basa en el uso de una clave de agrupamiento, que es un atributo o un conjunto de estos comunes a todas las tablas.

Todos los datos con el mismo valor de clase se guardan juntos en el mismo bloque si hay espacio. 
$\space$
### 2.1.Tipos de clusters
Hay dos tipos principales: 
+ B+ tree cluster
+ Hash cluster
$\space$
#### 2.1.1.B+ tree cluster
Utiliza un árbol B+ para almacenar los valores de la clave y el bloque donde se almacenan las filas que tienen ese valor. Funciona como un índice para todas las tablas del cluster. 

El parámetro `size` no es obligatorio.  Estima el número de claves que caben en un bloque. El tamaño suele ser blocksize/tamaño clave.

Es obligatorio crear un índice asociado.

```sql
create cluster clfact (codigo number(4)) size 1024;
create index idx_clusterfac on cluster clfact;

create table factura(
codfac number(4) constraint pk_factura primary key,
data date
) cluster clfact(codfac);

create table lina(
codfac number(4),
codlin number(3) constraint fk_factura references factura,
concepto char(40),
prezo number(5,2),
constraint pk_lina primary key(codfac,codlin)
) cluster clfact(codfac);
```
$\space$
#### 2.1.2.Hash cluster
Substituye el índice por una función hash aplicada a la clave de agrupamiento. Oracle preasigna espacio basándose en una estimación del valor que puede ocupar cada conjunto de valores que habrá por clave.

No es necesario crear un índice sobre el cluster. 

El parámetro `hashkeys` es el número estimado de claves de agrupamiento. Suele ser tamaño cluster / (blocksize/tamaño clave). 

```sql
create cluster clfact (codigo number(4))
hashkeys 100000;
```
$\space$
### 2.2.Ventajas e inconvenientes
El clusterizado puede ser útil, pero también tiene inconvenientes.
$\space$
#### 2.2.1.Ventajas
Ls ventajas de los clusters son:
+ [p] Hace que los join sean más eficientes.
+ [p] Mejora el buffer caché.
+ [p] Puede reducir la cantidad de índices necesarios en lugar de tener un índice por tabla.
+ [p] Se puede crear un cluster para una tabla sola con `single table`. Es útil para tablas de lookup, que con tablas clave-valor para buscar códigos.
$\space$
#### 2.2.2.Inconvenientes
+ [c] El escaneo secuencial puede ser más lento que una tabla heap.
+ [c] Las inserciones se ralentizan.
+ [c] El grado de clusterización es muy dependiente de la forma de gestionar los datos.
+ [c] La eficiencia depende mucho de la precisión del dimensionamiento.
$\space$
## 3.Index Organized Tables
Las IOT (Index Organized Tables) son tablas almacenadas en un índice. Funciona como un árbol B+, pero guarda los datos de la tabla en las hojas en lugar de rowIDs. 

La clave de indexación es la clave primaria de la tabla. Las entradas no tienen rowID porque se mueven al reestructurar el índice en las operaciones DML. 

Se puede crear un índice secundario con un rowID virtual para el valor de la clave primaria de las filas de la tabla.

```sql
create table pais(
id int constraint pk_pais primary key,
nome varchar(200) not null,
poboacion numeric(10)
) organization index;
```

![[iot.png]]
$\space$
### 3.1.Ventajas e inconvenientes
Las IOT también tienen ventajas e inconvenientes.
$\space$
#### 3.1.1.Ventajas
Las ventajas son:
+ [p] Es muy eficiente buscar por clave primaria.
+ [p] Ahorra espacio porque se guarda todo en el índice.
+ [p] Se mantiene la ordenación por clave.
$\space$
#### 3.1.2.Inconvenientes
+ [c] Las operaciones DML son más lentas que en una tabla heap.
+ [c]  Los índices secundarios no son muy eficientes.
