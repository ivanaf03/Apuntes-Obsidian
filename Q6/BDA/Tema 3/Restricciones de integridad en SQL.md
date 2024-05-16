[[Tema 3-Integridad]]
$\space$
## 1.Definición de restricciones
Se pueden crear restricciones al crear una tabla con `create table` o mediante `alter table add`. Se pueden eliminar con `alter table drop`.

```sql
create table empleados (
    id int primary key,
    nombre varchar(50),
    apellido varchar(50),
    edad int,
    salario decimal(10, 2),
    constraint chk_edad check (edad >= 18), -- Restricción de verificación de edad mínima
    constraint chk_salario check (salario >= 0) -- Restricción de verificación de salario no negativo
);

alter table empleados
add constraint chk_nombre check (nombre is not null); -- Restricción de verificación de nombre no nulo

```

En SQL se pueden crear restricciones a nivel de columna y a nivel de fila.
$\space$
### 1.1.Restricciones a nivel de columna
Son restricciones en los atributos, por ejemplo, claves primarias o atributos que no admiten nulos.

```sql
deptno numeric (2) constraint pk_dept primary key
```
$\space$
### 1.2.Restricciones a nivel de fila
Son restricciones que afectan a varios atributos.

```sql
constraint c_valid_date check (enddate > startdate)
```
$\space$
### 1.3.Ventajas de nombrar las restricciones
Las restricciones tienen nombre. Si no se lo damos se lo pondrá el sistema. Las ventajas de esto son:
+ [p] Se obtienen mensajes de violación de restricción más significativos.
+ [p]  Permite trabajar con ellas con facilidad.
$\space$
## 2.Tipos de restricciones
SQL permite especificar varios tipos de restricciones.
$\space$
### 2.1.Restricción de clave primaria
Las claves primarias no admiten nulos ni duplicados. Se especifican con `primary key`. Cada tabla solo puede tener una clave primaria.

```sql
create table dept(
    deptno numeric(2) primary key, -- sin nombre
    dname ...
);

create table dept(
    deptno numeric(2),
    dname ...,
    primary key (deptno) -- sin nombre
);

create table dept(
    deptno numeric(2) constraint pk_dept primary key, -- con nombre
    dname ...
);

create table dept(
    deptno numeric(2),
    dname ...,
    constraint pk_dept primary key (deptno) -- con nombre
);
```

Podemos eliminar restricciones y crearlas nuevas después.

```sql
alter table dept drop constraint pk_dept;

alter table dept add constraint pk_leave primary key (empno, startdate);
```
$\space$
### 2.2.Restricción de valores requeridos
Es una restricción que solo funciona a nivel de atributo, no de fila. Se especifica con `not null`. Evita que se creen filas con nulos en ese atributo y que si se actualizan las filas se traten de insertan nulos en él.

Si esta restricción se coloca sobre una clave foránea no tiene sentido indicar como acción referencial `set null`, ya que se pondrían como nulos los valores de claves primarias.

```sql
create table empleados (
    idempleado int primary key,
    nombre varchar(100) not null, -- restricción sin nombre
    apellido varchar(100),
    edad int
);

create table empleados (
    idempleado int primary key,
    nombre varchar(100) not null constraint notnull_nombre_empleado, -- restricción con nombre
    apellido varchar(100),
    edad int
);
```

```sql
-- Problema del set null

create table clientes (
    idcliente int primary key,
    nombre varchar(100)
);

create table pedidos (
    idpedido int primary key,
    idcliente int not null,
    fechapedido date,
    foreign key (idcliente) references clientes(idcliente)
    on delete set null -- Si se elimina un cliente, el IDCliente en los pedidos asociados se establecerá en NULL.
    on update set null -- Si se actualiza el IDCliente en Clientes, se actualizará el IDCliente en los pedidos asociados a NULL.
);

```
$\space$
#### 2.2.1.Peculiaridades
Esta restricción es bastante especial. Si se viola la restricción generalmente los gestores no indican el nombre de la restricción, ponen el nombre de la columna e indican que se está intentando poner un nulo en ella. Se guardan en el catálogo como restricciones `check is not null`. Para crear o eliminar estas restricciones es necesario modificar la columna asociada.
$\space$
### 2.3.Restricción de unicidad
Indica que un atributo o conjunto de atributos no admite duplicados en los valores no nulos. No implica que no se admitan nulos. Se especifica con `unique`.

 Las restricciones de clave primaria implican unicidad. Una clave candidata implica `not null` para cada atributo y `unique` para todo el conjunto de atributos.

```sql
create table usuarios (
    id int primary key,
    nombre varchar(50) not null,
    correo varchar(100) unique
);

create table ventas (
    id_venta int primary key,
    producto varchar(100),
    fecha date,
    cantidad int,
    unique (producto, fecha)
);
```
$\space$
### 2.4.Restricción de integridad referencial
La integridad referencial es un concepto que garantiza que las relaciones entre las tablas en una base de datos se mantengan válidas y consistentes. Para ello se usan las claves foráneas. Indican que los valores de la clave foránea deben de existir entre los valores de la clave candidata a a que referencian o ser nulos. Pueden referenciar tanto a la misma tabla como a otra.
$\space$
#### 2.4.1.Definición de foráneas
Las claves foráneas se pueden definir:
- **A nivel de atributo:** `deptno number(2) constraint fk_dept references dept(deptno)`
- **A nivel de fila:** `constraint fk_mgr foreign key (mgr) references emp`
$\space$
#### 2.4.2.Interacción con otras tablas
El resto de restricciones solo afectan a la propia tabla. La restricción de clave foránea afecta a las tablas que referencia.

Al hacer una inserción o actualización en la tabla que contiene la foránea, esta solo puede ser actualizada con nulos o valores de la clave candidata a la que referencian. Si no salta un error.

Para hacer borrados y actualizaciones en la tabla referenciada se indica el tipo de acción referencial que se va a llevar a cabo con `on delete` y `on update`:
+ **No action:** no se hace el borrado o actualización y salta un error si los cambios afectan a la integridad referencial.
+ **Cascade:** modifica o elimina en cascada todos los cambios de la tabla referenciada.
+ **Set null:** actualiza a null los campos de clave foránea en las filas afectadas.
+ **Set default:** actualiza al valor establecido por defecto los campos de clave foránea en las filas afectadas.
$\space$
#### 2.4.3.Claves encadenadas
Por ejemplo, si tenemos las tablas `emp`, `dept` y `leave`, con las restricciones `dept<-emp<-leave` del ejemplo anterior puede haber problemas al eliminar un departamento:
+ Si ambas son en cascada se eliminarían todos los empleados y todas las bajas asociadas a ellos.
+ Si las bajas están definidas como `no action` se intentarían eliminar todos los empleados, pero como para ello se tendrían que eliminar antes las bajas asociadas y no se puede, se produce un error.
$\space$
#### 2.4.4.Ciclos referenciales
Un ciclo referencial es una referencia de una tabla a si misma, ya sea ella misma o a través de otras tablas.

Pueden ocasionar problemas:
+ [c] Borrados masivos recursivos. Por ejemplo, si la clave foránea del jefe en la tabla `emp` estuviera definida en cascada, al eliminar al jefe más alto de todos se eliminaría toda la tabla de empleados.
+ [c] Si `emp.detno` y `dept.dirno` no admiten nulos, si partimos de una BBDD vacía no podemos introducir datos.
$\space$
#### 2.4.5.Cláusula match
Permite aceptar claves candidatas a las que referencia una foránea en función de los valores nulos que contenga. Solo tiene sentido cuando la clave candidata tiene más de un atributo. Puede ser:
+ **Match simple:** verifica la restricción si alguno de los campos es nulo o si ninguno es nulo y toda la clave candidata aparece en la clave candidata.
+ **Match partial:** verifica la restricción si para cada uno de sus campos o es nulo o aparece en la clave candidata.
+ **Match full:** verifica la restricción si todos los campos son nulos o ninguno es nulo y toda la clave candidata aparece en la clave candidata.

![[match 1.png]]

![[match 2.png]]
$\space$
### 2.5.Restricción de comprobación
Las restricciones check permiten hacer una validación de valores para un atributo, una fila, un dominio o una aserción.

```sql
-- A nivel de atributo

create table productos (
    producto_id int primary key,
    nombre varchar(100),
    precio decimal(10, 2) check (precio > 0)
);


-- A nivel de fila

create table empleados (
    empleado_id int primary key,
    nombre varchar(100),
    salario decimal(10, 2),
    salario_maximo decimal(10, 2),
    constraint ck_salario check (salario <= salario_maximo)
);
```
$\space$
#### 2.5.1.Problemas con subconsultas
Los SGBD no permiten el uso de subconsultas en el check por la cantidad de problemas que podrían ocasionar.

```sql
check (sal <= (select max(sal) from emp));
-- Se ejecutaría en cada inserción o actualización y sería muy costoso

check (deptno in (select deptno from dept));
-- En tablas grandes tendría el mismo problema que la anterior

check(unique (select id from tab1 union all select id from tab2));
-- Comprueba que los ID sean únicos en ambas tablas. Cuanto más grandes sean mucho menor sería el rendimiento

check (estado in ('APROBADO', 'DENEGADO'));
-- Si hubiera más estados en un futuro habría que añadirlos a la restricción

check (provincia in ('A Coruña', 'Lugo', 'Ourense', 'Pontevedra', 'Asturias', 'Cantabria', ...));
-- Lo mismo que el anterior
```
$\space$
#### 2.5.2.Dominios
Un dominio es un tipo de dato que puede ir asociado con una restricción que especifique los valores válidos de ese tipo. Permite crear atributos de ese tipo.

```sql
create domain salario as number(7,2)
  constraint c_valid_sal_domain check(value > 1080);

create table emp (
  ...
  sal salario,
  ...
);

-- Se pueden añadir y eliminar restricciones
alter domain salario drop constraint c_valid_sal_domain;
alter domain salario add constraint new_constraint check(value < 5000);
```
$\space$
#### 2.5.3.Aserciones
Una aserción es una restricción a nivel de BBDD. Reaccionan ante inserciones y actualizaciones en las tablas implicadas. Dado que los SGBD no las suelen implementar, hay que usar triggers en su lugar.

```sql
create assertion as_similar_salaries
check( ( (select max(sal) from emp) -
(select min(sal) from emp) ) <100);

create assertion as_small_depts
check (not exists
(select deptno from emp
group by deptno
having count(*)>10));
```
$\space$
### 2.6.Triggers
Un trigger o regla ECA es la ejecución de una acción cuando se produce un evento que cumple una condición. Se basan en programación orientada en eventos.

```sql
-- En el estándar para implementar "as_small_depts"

create trigger t_emp_small_depts_au
after update on emp
for each statement
when ( exists (select deptno from emp
group by deptno
having count(*) > 10))
signal sqlstate '99001',
'Departamento demasiado grande';

create trigger t_emp_small_depts_ais
after insert on emp
for each statement
when ( exists (select deptno from emp
group by deptno
having count(*) > 10))
signal sqlstate '99001',
'Departamento demasiado grande';


-- En Oracle para implementar "as_small_depts"

create trigger t_emp_small_depts_aus
after insert or update on emp
declare
  n number;
begin
  select count(*) into n
  from (select deptno from emp
  group by deptno
  having count(*) > 10);
  if n > 0 then
    raise_application_error(-20001,
    'Departamento demasiado grande');
  end if;
end;
```
$\space$
### 2.7.Restricciones aplazadas
Una restricción puede ser `deferrable` si la comprobación se hace al confirmar la transacción. Se define como:

```sql
constraint <nombre> <definición>
{ not deferrable |
  deferrable initially { deferred | immediate }
}
```

Por defecto está a `not deferrable`. Las restricciones en este modo se comprueban al realizar la consulta DML. Con `initially immediate`, las restricciones también se comprueban al realizar la consulta DML, pero no hacen rollback, solo anulan la inserción o actualización.

Se puede cambiar el modo de comprobación con:

```sql
set constraints {all | restr1 [restr2, ...]} {immediate | deferred}
```
$\space$
#### 2.7.1.Funcionamiento
Cuando una sentencia DML afecta a una restricción:
+ Si está en modo inmediato se comprueba y, si falla, se anula la sentencia.
+ Si está en modo aplazado no se comprueba hasta hacer commit. Al hacerlo, si falla alguna, se hace un rollback completo de la transacción.
$\space$
#### 2.7.2.Ejemplos

```sql
-- Modo aplazado
create table test1(
    v numeric(3),
    constraint c_vpositive check (v > 0)
    deferrable initially deferred
);

insert into test1 values(1);
insert into test1 values(0); 
commit; -- Se comprueba en el commit, fallo y rollback

select * from test1; -- No hay filas

-- Modo inmediato
set constraints c_vpositive immediate; 

insert into test1 values(1); -- Comprueba, OK
insert into test1 values(0); -- Comprueba, fallo y anula el insert
commit;

select * from test1; -- Fila con valor 1
```
$\space$
#### 2.7.3.Ventajas
Las restricciones aplazadas sirven para:
+ [p] Solucionar el problema mencionado antes de los ciclos referenciales con restricciones de `not null`. 
+ [p] Realizar una transacción que una vez terminada cumpla las reglas de integridad, pero durante la transacción puede que no. 
