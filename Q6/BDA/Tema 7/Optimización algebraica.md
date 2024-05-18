[[Tema 7-Optimización]]
$\space$
## 1.Operadores de álgebra relacional

![[algebra relacional.png]]

![[group by.png]]

![[order by.png]]

Nota: ejercicios y ejemplos en papel
$\space$
## 2.Optimización
La optimización algebraica se basa en heurística. No utiliza información asociada a tablas, como el número de filas. Utiliza equivalencias algebraicas. 

Se basa en descartar lo antes posible todos los datos que no hacen falta para resolver la consulta. La salida se denomina forma canónica.
$\space$
### 2.1.Reglas

![[algebra 1.png]]

![[algebra 2.png]]

![[algebra 3.png]]

Nota: ejercicios y ejemplos en papel

Las reglas de la heurística se basan en:
+ Se bajan las selecciones lo máximo posible
+ Se descartan lo antes posible los atributos no necesarios mediante proyecciones
+ Se sustituyen los productos cartesianos por joins
+ Se ordenan los joins, primero se hacen los más restrictivos