[[Catálogo]]

# Consultas
## Consultas de usuario
Un usuario puede consultar el catálogo para saber las columnas de la tabla `emp`:
```sql
select column_name, data_type
from information_schema.columns
where table_name='EMP';
```

## Consultas de sistema
```sql
select *
from emp
where sal+comm>2000
and deptno=10;
```
+ [<] **Mediante el catálogo:**
+ El SGBD comprueba que `emp` exista y sea una tabla o vista.
+ Comprueba que el usuario tiene permiso para hacer `select`.
+ Saca toda la lista de columnas.
+ Comprueba que las columnas que satisfacen el `where` existen y son del tipo adecuado.
+ Comprueba si existen índices, por ejemplo, para optimizar la consulta.

# Contenido del catálogo
![[esquema conceptual externo fisico.png]]

El catálogo almacena datos de los esquemas conceptual, físico y externo.

+ [<] **Contiene:**
+ Definición de tablas y columnas.
+ Restricciones de integridad.
+ Definición de vistas.
+ Descripción de los espacios de almacenamiento.
+ índices.
+ Información sobre usuarios, roles y privilegios.
+ Descripción de estructuras lógicas y físicas de la BD.
+ Metadatos del propio catálogo.

No contiene información externa a la base de datos, como la definición de los datos, su uso o los programas que los manipulan.

