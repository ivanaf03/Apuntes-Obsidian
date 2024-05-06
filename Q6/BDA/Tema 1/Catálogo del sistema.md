[[Tema 1-Catálogo]]
$\space$$\space$
## 1.Consultas al catálogo
El catálogo puede ser consultado tanto por usuarios como por el propio sistema.
$\space$$\space$
### 1.1.Consultas de usuario
Un usuario puede consultar el catálogo para saber, por ejemplo, las columnas de una tabla mediante el catálogo:

```sql
select column_name, data_type
from information_schema.columns
where table_name='emp';
```
$\space$$\space$
### 1.2.Consultas de sistema
Cuando el usuario hace una consulta, el SGBD consulta el catálogo. Por ejemplo:

```sql
select *
from emp
where sal+comm>2000
and deptno=10;
```

El SGBD comprueba que existe en el sistema la tabla o vista `emp`. Depués comprueba que el usuario tiene permiso para hacer el `select` sobre `emp`. Selecciona todas las columnas de la tabla y aplica la condición del `where`, comprobando que existan las columnas y que son del tipo adecuado, por ejemplo, para que se puedan sumar `sal` y `comm`. Además hace la consulta más óptima buscando índices, identificando los espacios de almacenamiento, etc. 

El gestor saca toda esta información del catálogo.
$\space$$\space$
## 2.Contenido del catálogo
El catálogo contiene datos de los tres niveles de la arquitectura ANSI/SPARC.
$\space$$\space$
### 2.1.Arquitectura ANSI/SPARC
La arquitectura ANSI/SPARC es una división en tres niveles de la estructura de una base de datos. Sirve para separar la vista de los usuarios de la complejidad interna y los detalles físicos de almacenamiento.

![[esquema conceptual externo fisico.png]]
$\space$$\space$
#### 2.1.1.Niveles
Se basa en tres niveles:
+ **Externo:** vista que tienen los usuarios finales de la base de datos.
+ **Conceptual:** lógica global de la base de datos. Describe como se almacenan los datos y como se relacionan entre sí. Define las entidades, relaciones y restricciones de integridad.
+ **Interno:** forma en que se almacenan físicamente los datos en el sistema. Define la estructura de almacenamiento, los índices y los mecanismos de acceso a datos.
$\space$$\space$
### 2.2.Elementos del catálogo
El catálogo no contiene información externa a la base de datos, como el significado de los datos, para que se usan o que programas los manipulan.

Principalmente el catálogo contiene:
+ Definiciones de tablas, vistas y sus columnas.
+ Restricciones de integridad.
+ Descripción de los espacios de almacenamiento.
+ índices asociados a las tablas.
+ Información sobre usuarios, roles y privilegios.
+ Descripción de las estructuras lógicas y físicas de la BD.
+ Metadatos del propio catálogo.

