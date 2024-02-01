[[Catálogo]]

## Consultas
### Consultas de usuario
Podemos consultar las columnas de la tabla `emp`:
```sql
select column_name, data_type
from information_schema.columns
where table_name='EMP';
```

### Consultas de sistema
```sql
select *
from emp
where sal+comm>2000
and deptno=10;
```

Al realizar esta consulta el SGBD consulta el catálogo del sistema para realizar todas las operaciones y comprobaciones internas.

## Contenido
![[esquema conceptual externo fisico.png]]

El catálogo almacena datos de los esquemas conceptual, físico y externo. Contiene, entre otros elementos:
+ Definición de tablas y columnas.
+ Restricciones de integridad.
+ Definición de vistas.
+ Descripción de los espacios de almacenamiento.
+ índices.
+ Información sobre usuarios, roles y privilegios.
+ Descripción de estructuras lógicas y físicas de la BD.
+ Metadatos del propio catálogo.

No contiene información externa a la base de datos.

