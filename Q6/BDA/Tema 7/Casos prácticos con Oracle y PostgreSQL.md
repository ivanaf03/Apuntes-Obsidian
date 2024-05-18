[[Tema 7-Optimización]]
$\space$
## 1.Optimizador de Oracle
Oracle contaba con un optimizador basado en reglas, RBO, que se ha quedado obsoleto; y otro basado en costes, CBO. Este último es mucho más eficiente. Genera planes contando con las estadísticas de la base de datos actualizada.

Su objetivo es:
+ Reducir tiempo de respuesta.
+ Mejorar el rendimiento.
$\space$
### 1.1.Optimizer mode
Es un parámetro que se puede usar para cambiar el objetivo global:
+ **All_rows:** maximiza el rendimiento para obtener todas las filas.
+ **First_rows_n:** n puede valer 10, 100 o 1000. Minimiza el tiempo de respuesta para obtener esas n primeras filas.
+ **First_rows:** combina costes y heurísticas para obtener las primeras filas en general.
$\space$
#### 1.1.1.Cambio de modo
Se puede cambiar de modo en una sesión con:

```sql
alter session set optimizer_mode=<modo>
```

O para un DBA en todo el sistema con:

```sql
alter system set optimizer_mode=<modo>
```

Para una consulta se pueden usar hints.
$\space$
### 1.2.Actualización de estadísticas
Podemos actualizar las estadísticas con:

```sql
call dbms_stats.gather_table_stats('"miguel.penabad"','TEST');
-- Actualiza una tabla

call dbms_stats.gather_schema_stats('SCOTT');
-- Actualiza todas las tablas del esquema
```
$\space$
### 1.3.Planes de ejecución
Oracle optimiza todo tipo de consultas. Podemos ver el plan de ejecución de dos formas:
+ **Sin ejecutar la consulta:** se hace con `explain plan for <consulta>`.

![[explain plan.png]]

+ **Con autotrace:** se hace con `set autotrace {off | on | trace [only]} [explain] [statistics]` y ejecuta la consulta además de mostrar el plan de ejecución.

![[set autotrace.png]]
$\space$
#### 1.3.1.Interpretación
Nota: ver ejemplos en diapos

![[ejemplo 1 plan.png]]

Con `operation` se indica el procedimiento de bajo nivel usado. La primera línea es la sentencia SQL. Lo que está indentado depende de lo de arriba. Con `name` se indica el nombre de la tabla accedida. El acceso a solo la información necesaria se indica con `access` y con `filter` se eliminan datos innecesarios.

El optimzador usa:
+ **Table access full:** exploración completa de tabla.
+ **Table access by index rowid:** acceso a filas individuales por rowids.
+ **Table access by index rowid batched:** mejora del anterior.
+ **Index unique scan:** búsqueda de índice único.
+ **Index range scan:** recorrido ordenado en un rango a través de un índice.
+ **Index full scan:** exploración ordenada completa del índice.
+ **Index fast full scan:** exploración desordenada completa del índice.
+ **Index skip scan:** búsquedas sin los primeros atributos.
+ **Sort join:** ordenación para merge join posterior.
+ **Sort order by:** ordenación por `order by`.
+ **Hash unique:** eliminación de duplicados.
+ **Sort unique:** ordenación de datos para eliminar duplicados.
+ **Sort unique no sort:** eliminación de datos previamente ordenados.
+ **Hash group by:** agrupa las filas en una tabla hash y calcula los agregados.
+ **Sort group by:** ordena los datos para hacer grupos y calcula los agregados.
+ **Sort group by nosort:** calcula los agregados a partir de filas ya ordenadas.
+ **Sort aggregate:** obtiene una fila con los valores agregados de un grupo de filas.
$\space$
## 2.Hints
Los hints son indicadores para recomendar al optimizador que siga ciertas estrategias.
Se escriben en un comentario que empieza por +.
$\space$
### 2.1.Para el optimizador

```sql
select /*+first rows(100)*/ empno from emp;

select /*+all_rows*/ empno from emp;
```
$\space$
### 2.2.Para joins
Podemos usar:
+ **Ordered:** orden normal.
+ **Use_nl:** nested loop join.
+ **Use_merge:** sort-merge join.
+ **Use hash:** hash join.
$\space$
### 2.3.Para acceso a datos
Podemos usar:
+ **Full:** toda la tabla.
+ **Index:** usar índices especificados.
+ **No_index:** deshabilitar los índices.



