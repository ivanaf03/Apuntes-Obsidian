[[Diseño físico]]

# 1.Zonas lógicas y físicas
Una zona lógica de almacenamiento de datos es la abstracción de una o más zonas físicas de almacenamiento de datos. Al crear una tabla se especifica la zona lógica, no la zona física. También se llaman `tablespace` en Oracle, MySQL, etc. o `filegroup` en MS SQL Server.

Las zonas físicas generalmente son ficheros del sistema operativo. También pueden ser otros dispositivos o particiones, gestores de volumen propios como Oracle ASM, etc.

## 1.1.Ejemplos

```sql
--En Oracle
create tablespace ts1
add datafile '/u01/data/ts1.dbf'
size 200m autoextend on;

create table emp(
empno number(3) ....
) tablespace ts1;

--En MS SQL Server
alter database bd1 add filegroup fg1;
alter database bd1 add file
( name = fg01,
filename = 'C:\Data\fg01.ndf',
size = 200mb, filegrowth = 5mb)
to filegroup fg1;

create table emp(
empno number(3) ....
) on fg1;
```

## 12..Oracle
En Oracle un `tablespace` está formado por ficheros de datos. Crea algunos de forma automática:
+ [>] *`SYSTEM`:* catálogo del sistema, tablas y vistas administrativas, objetos compilados, etc.
+ [>] *`SYSAUX`:* sirve como apoyo de `SYSTEM` para componentes de Oracle.
+ [>] *`UNDOTBS1`:* para deshacer registros, rollbacks y consistencia de lectura.
+ [>] *`TEMP`:*  datos temporales usados en consultas.
+ [>] *`USERS`:* objetos de usuarios.

# 2.Espacios asociados a objetos
Algunos gestores denominan segmento a los datos almacenados por un objeto. Pueden ocupar varios ficheros físicos, pero siempre están asociados a una sola zona lógica de almacenamiento.

Los segmentos están formados por extensiones, conjuntos continuos de bloques de tamaño fijo o variable. Los bloques son registros que almacenan filas de longitud variable. Pueden tener tamaño fijo o variable dependiendo del gestor, pero es múltiplo del tamaño de bloque del sistema operativo (suele ser 8kB).

# 3.Organización de tablas
Las tablas se suelen organizar como `heap tables`. Se añaden las filas en cualquier lugar donde haya espacio, por lo que las inserciones son muy eficientes. No están ordenadas las filas. 

Las desventajas de esta organización son:
+ [c] Tras hacer borrados pueden quedar con huecos.
+ [c] Las búsquedas no son eficientes.

## 1.1.Otras organizaciones
Otras posibles organizaciones son:
+ Tablas almacenadas como índices.
+ Clusters.

