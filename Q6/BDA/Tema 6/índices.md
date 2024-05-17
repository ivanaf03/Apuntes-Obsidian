[[Tema 6-Diseño físico]]
$\space$
## 1.Acceso sin índices
La selectividad de una consulta es inversamente proporcional al porcentaje de filas que devuelve. Una selectividad alta devuelve un porcentaje bajo de filas.

Es interesante acceder directamente a la tabla cuando hay baja selectividad. Se lee toda la zona de almacenamiento de forma secuencial. Cuando hay alta selectividad muchas de las lecturas no dan resultado, por lo que es muy poco eficiente.

![[selectividad bd.png]]
$\space$
## 2.índices
Un índice indica donde se encuentran los datos buscados de forma similar a un índice de un libro. Ofrece un camino alternativo a la exploración secuencial de la tabla.

Una clave de indexación es un atributo o conjunto de atributos que se utiliza para identificar de manera única cada fila en una tabla. Los índices almacenan entradas, formadas por valores de clave de indexación y la posición física que ocupan, el `rowid`. Suelen estar ordenados por clave de indexación.
$\space$
### 2.1.índices en árbol
Los índices más comunes son los que tienen forma de árbol B+. Se caracteriza por:
+ Es un árbol balanceado.
+ Los nodos hoja contienen las claves de indexación y el `rowid`. Están enlazados entre ellos.
+ Los valores de clave de los nodos intermedios también están en los nodos hoja. 

$\space$
![[árbol B+.png]]

https://eduarmandov.wordpress.com/wp-content/uploads/2017/05/datastructures-c3a1rboles-b-informacion.pdf
$\space$
### 2.2.Acceso a datos a través de índices
Con alta selectividad el acceso es eficiente porque se accede al índice y este hace lecturas diferenciadas a pocas zonas de la tabla. Con baja selectividad habría muchas lecturas y bajaría la eficiencia.
$\space$
### 2.3.Creación y borrado de índices
El estándar SQL no contempla los índices. La sintaxis suele ser la misma en los diferentes SGBD.

```sql
--Oracle
create index i_emp_sal on emp(sal);

create unique index i_dept_dname on dept(dname);

drop index i_emp_sal;
```

Los gestores pueden crear índices automáticamente a partir de las restricciones. Por ejemplo, lo hacen al crear claves primarias y, algunos gestores, sobre las claves foráneas.
$\space$$\space$
### 2.4 Ventajas e inconvenientes
Los índices tiene ventajas e inconvenientes.
$\space$
#### 2.4.1.Ventajas
Las ventajas del uso de índices son:
+ [p] Aceleran los `select`, `deletes` y `updates`.
+ [p] Evita acceder a zonas de disco que no contienen los datos que se buscan.
+ [p] Pueden evitar el acceso a la tabla cuando todos los datos necesarios están en el índice. Esta estrategia se llama `index only`.
+ [p] Pueden acelerar los datos ordenados por clave de indexación.
+ [p] Existen otros índices, a parte de los árboles B+, útiles para recuperar un porcentaje alto de filas.
$\space$
#### 2.4.2.Inconvenientes
Los inconvenientes del uso de índices son:
+ [c] Ocupan espacio en disco.
+ [c] Retardan las operaciones DML.
+ [c] No siempre son adecuados.
+ [c] Si el optimizador no utiliza un índice este ralentizará las operaciones DML.
$\space$
### 2.5.Tipos de índices
Según varios factores, los índice pueden ser de muchas formas.
$\space$
#### 2.5.1.Según los valores en la clave de indexación
Pueden ser:
+ **Únicos:** la clave no admite duplicados. Son de tipo `unique`.
+ **No únicos:** la clave admite duplicados.

```sql
create unique index i_dept_dname on dept(dname);

create index i_emp_sal on emp(sal);
```
$\space$
#### 2.5.2.Según el número de columnas de clave de indexación
Pueden ser:
+ **Simples:** el índice está definido sobre una sola columna.
+ **Compuestos:** el índice está definido sobre varias columnas.

```sql
create index i_emp_sal on emp(sal);

create index i_emp_sal_job on emp(sal, job);
```
$\space$
#### 2.5.3.Según la existencia de entradas
Pueden ser:
+ **Denso:** existe una entrada por cada fila.
+ **Disperso:** no hay una entrada por cada fila, es agrupado.

```sql
-- Ejemplo de un índice denso (cada fila tiene una entrada en el índice)
create index i_emp_denso on emp(empno);

-- Ejemplo de un índice disperso (no todas las filas tienen una entrada en el índice, se basa en agrupaciones)
-- Supongamos que tenemos una tabla 'orders' con una columna 'order_date' 
-- y queremos crear un índice agrupado basado en el año y mes de 'order_date'.
create index i_orders_date on orders(trunc(order_date, 'MM'));
```
$\space$
#### 2.5.4.Según el orden de los datos
Pueden ser:
+ **No agrupado o secundario:** los datos no están ordenados por clave de indexación. Permite más de un índice de este tipo.
+ **Agrupado:** la tabla está ordenada por clave de indexación. Suele ser el índice sobre la clave primaria y se conoce como índice primario. Suelen ser eficientes en consultas por rango.
$\space$
## 3.índices en Oracle
Oracle permite varios tipos de índices:
+ **índices predeterminados:** son un árbol B+.

```sql
create index i_emp_mgr on emp(mgr);
```

+ **De clave inversa:** invierten la clave de indexación para evitar contenciones en valores autoincrementales:

```sql
create index i_emp_mgr on emp(mgr) reverse;
```

+ **Basados en funciones:** indexa expresiones sobre consultas:

```sql
create index i_emp_saltotal on emp(sal + comm);
create index i_emp_saldesc on emp(sal desc);
create index i_emp_upename on emp(upper(ename));
```
$\space$
### 3.1.índice bitmap
Tiene forma de árbol. En lugar de almacenar rowIDs almacena mapas de bits con tantas posiciones como filas tiene el valor. En cada posición se indica 1 o 0 para el valor.

![[bitmap index.png]]

```sql
create bitmap index i_taboa_cor on taboa(cor);
```

Son muy útiles para columnas con cardinalidad baja, es decir, pocos valores diferentes. Funcionan muy bien si se sufren pocas modificaciones. Permiten optimizar consultas con and y or.

![[bitmap example.png]]
$\space$
### 3.2.Características de Oracle
No indexa los valores nulos. Cuando se realizan operaciones DML se actualizan los índices de forma coherente. 

El optimizador decide si usar o no los índices. Podemos hacerlos visibles o invisibles para el optimizador.

```sql
create index i_dept_dname on dept(dname) invisible;
alter index i_dept_dname visible;
alter index i_dept_dname invisible;
```
$\space$
### 3.3.Columnas que hay que indexar
El gestor indexa las columnas que son claves primarias o tienen restricciones de unicidad. 

Se deben indexar las claves foráneas para optimizar los joins o cualquier otra que aparezca en algún join. Además, se deben indexar las columnas usadas con frecuencia para filtrar los resultados, para ordenar con `order by` o agrupar o las que permiten resolver consultas con solo acceder al índice.

No se deben indexar ls columnas que se actualizan con mucha frecuencia.