[[Diseño físico]]

# 1.Acceso sin índices
La selectividad de una consulta es inversamente proporcional al porcentaje de filas que devuelve. Una selectividad alta devuelve un porcentaje bajo de filas.

Es interesante acceder directamente a la tabla cuando hay baja selectividad. Lee toda la zona de almacenamiento de forma secuencial. Cuando hay alta selectividad muchas de las lecturas no dan resultado, por lo que es muy poco eficiente.

# 2.índices
Un índice indica donde se encuentran los datos buscados de forma similar a un índice de un libro. Ofrece un camino alternativo a la exploración secuencial de la tabla.

Almacenan entradas, formadas por valores de clave de indexación, que pueden ser uno o más campos de la tabla, y la posición física que ocupan, el `rowid`.

Suelen ordenarse por clave de indexación.

## 2.1.índices en árbol
Los índices más comunes son los que tienen forma de árbol B+. Esta estructura:
+ [>] Es un árbol balanceado.
+ [>] Los nodos hoja contienen las claves de indexación y el `rowid`. Están enlazados entre ellos.
+ [>] Los valores de clave de los nodos intermedios también están en los nodos hoja. 

![[árbol B+.png]]

## 2.2.Acceso a datos a través de índices
Con alta selectividad el acceso es eficiente porque se accede al índice y este hace lecturas diferenciadas a pocas zonas de la tabla. Con baja selectividad habría muchas lecturas y bajaría la eficiencia.

## 2.3.Creación y borrado de índices
El estándar SQL no contempla los índices. La sintaxis suele ser la misma en los diferentes SGBD.

```sql
--Oracle
create index i_emp_sal on emp(sal);
create unique index i_dept_dname on dept(dname);
drop index i_emp_sal;
```

Los gestores pueden crear índices automáticamente a partir de las restricciones. Por ejemplo, lo hacen al crear claves primarias y, algunos gestores, sobre las claves foráneas.

## 2.4 Ventajas e inconvenientes
### 2.4.1.Ventajas
Las ventajas del uso de índices son:
+ [p] Aceleran los `select`, `deletes` y `updates`.
+ [p] Evita acceder a zonas de disco que no contienen los datos que se buscan.
+ [p] Pueden evitar el acceso a la tabla cuando todos los datos necesarios están en el índice. Esta estrategia se llama `index only`.
+ [p] Pueden acelerar los datos ordenados por clave de indexación.
+ [p] Existen otros índices, a parte de los árboles B+, útiles para recuperar un porcentaje alto de filas.

### 2.4.2.Inconvenientes
Los inconvenientes del uso de índices son:
+ [c] Ocupan espacio en disco.
+ [c] Retardan las operaciones DML.
+ [c] No siempre son adecuados.
+ [c] Si el optimizador no utiliza un índice este ralentizará las operaciones DML.

## 2.5.Tipos de índices
