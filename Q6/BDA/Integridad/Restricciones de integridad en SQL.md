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




