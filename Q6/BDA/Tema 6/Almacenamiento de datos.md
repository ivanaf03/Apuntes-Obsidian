[[Tema 6-Diseño físico]]
$\space$$\space$
## 1.Zonas lógicas y físicas
Una zona lógica de almacenamiento de datos es la abstracción de una o más zonas físicas de almacenamiento de datos. Al crear una tabla se especifica la zona lógica, no la zona física. También se llaman `tablespace` en Oracle, MySQL, etc. o `filegroup` en MS SQL Server.

Las zonas físicas generalmente son ficheros del sistema operativo. También pueden ser otros dispositivos o particiones, gestores de volumen propios como Oracle ASM, etc.
$\space$
### 1.1.Ejemplos

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
$\space$
### 1.2.Tablespace en Oracle
En Oracle un `tablespace` está formado por ficheros de datos. Crea algunos `tablespace` de forma automática:
+ **SYSTEM:** catálogo del sistema, tablas y vistas administrativas, objetos compilados, etc.
+ **SYSAUX:** sirve como apoyo de `SYSTEM` para componentes de Oracle.
+ **UNDOTBS1:** para deshacer registros, rollbacks y consistencia de lectura.
+ **TEMP:**  datos temporales usados en consultas.
+ **USERS:** objetos de usuarios.
$\space$
## 2.Espacio asociado a un objeto
Algunos gestores como Oracle llaman segmento a los datos almacenados por un objeto como sus tablas e índices. Se almacenan dentro de la misma zona lógica, aunque puede estar en varios ficheros.

Los segmentos están formados por extensiones, que son un conjunto de bloques contiguos en un fichero. Sirven como unidades de asignación de espacio.

Los bloques sirven para almacenar filas. El tamaño de un bloque es múltiplo del tamaño de bloque del sistema de ficheros. Puede ser de longitud fija o variable.

![[segmentos oracle.png]]
$\space$
## 3.Organización de tablas
Las tablas se suelen organizar como `heap tables`. Se añaden las filas en cualquier lugar donde haya espacio, por lo que las inserciones son muy eficientes. No están ordenadas las filas. 
$\space$
### 3.1.Desventajas de las heap tables
Las heap tables tienen ciertos problemas:
+ [c] Tras hacer borrados pueden quedar con huecos.
+ [c] Las búsquedas no son eficientes.
$\space$
### 3.2.Otras organizaciones
Otras posibles organizaciones son:
+ Tablas almacenadas como índices ordenadas por clave primaria.
+ Clusters.

