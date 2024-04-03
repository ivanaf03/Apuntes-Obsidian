[[Tema 1-Catálogo]]

## 1.Consultas al catálogo
Las consultas al catálogo pueden ser:
+ Consultas de usuario
+ Consultas del sistema
### 1.1.Consultas de usuario
Un usuario puede consultar el catálogo para saber, por ejemplo, las columnas de una tabla mediante el catálogo:

```sql
select column_name, data_type
from information_schema.columns
where table_name='emp';
```

### 1.2.Consultas de sistema
Cuando el usuario hace una consulta el SGBD consulta el catálogo. Por ejemplo:

```sql
select *
from emp
where sal+comm>2000
and deptno=10;
```

El SGBD:
+ Comprueba que `emp` exista y sea una tabla o vista.
+ Comprueba que el usuario tiene permiso para hacer `select`.
+ Saca toda la lista de columnas.
+ Comprueba que las columnas que satisfacen el `where` existen y son del tipo adecuado.
+ Comprueba si existen índices, por ejemplo, para optimizar la consulta.

## 2.Contenido del catálogo
El catálogo almacena datos de los esquemas:
+ **Externo:** vista que tienen los usuarios o aplicaciones sobre la base de datos.
+ **Conceptual:** visión global de la base de datos.
+ **Interno:** estructura física que define como guardar los datos.

$\space$
![[esquema conceptual externo fisico.png]]

### 2.1.Elementos
El catálogo contiene:
+ Definición de tablas y columnas.
+ Restricciones de integridad.
+ Definición de vistas.
+ Descripción de los espacios de almacenamiento.
+ índices.
+ Información sobre usuarios, roles y privilegios.
+ Descripción de estructuras lógicas y físicas de la BD.
+ Metadatos del propio catálogo.

$\space$
No contiene información externa a la base de datos, como la definición de los datos, su uso o los programas que los manipulan.

