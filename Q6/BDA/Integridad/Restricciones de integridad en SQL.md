[[Tema 3-Integridad]]

# Restricciones
+ [<] **Pueden ser:**
+ *A nivel de columna:* en los atributos, por ejemplo, atributos que no permiten nulos o claves primarias de un solo atributo.
```sql
deptno numeric(2) constraint pk_dept primary key
```
+ *A nivel de fila:* implican varios atributos.
```sql
constraint c_valid_date check (enddate>startdate)
```

Se pueden crear restricciones al crear la tabla con `create table` o mediante `alter table add`. Se puede eliminar una restricción con `alter table drop`.

Las restricciones tienen nombre. Si no se lo damos se lo pone el sistema por defecto. Es muy útil darles nombre.

## Restricción de clave primaria
Las claves primarias no admiten nulos ni duplicados. Se especifican con la restricción `primary key`. Las tablas solo pueden tener una clave primaria.

```sql
create table dept(
    deptno numeric(2) primary key,
    dname ...
);

create table dept(
    deptno numeric(2),
    dname ...,
    primary key (deptno)
);

create table dept(
    deptno numeric(2) constraint pk_dept primary key,
    dname ...
);

create table dept(
    deptno numeric(2),
    dname ...,
    constraint pk_dept primary key (deptno)
);
```

Podemos eliminar o añadir restricciones con `alter table`:
```sql
alter table dept drop constraint pk_dept;
alter table leave add constraint pk_leave primary key(empno, startdate);
```

## Restricción de valores requeridos
Esta restricción solo se aplica a nivel de atributo. Garantiza que no se puede insertar una fila con un nulo en ese atributo, que no se puede actualizar ese atributo a nulo y, si forma parte de una clave foránea, no tendría sentido especificar como acción referencial `set null`.

```sql
create table emp(
    ...
    ename varchar(50) not null,
    ...
);

create table emp(
    ...
    ename varchar(50) constraint nn_ename not null,
    ...
);
```

## Restricción de unicidad
Indica que los atributos o conjuntos de atributos no admiten valores duplicados en atributos no nulos. No implica que no admita nulos. Una clave candidata formada por un conjunto de columnas implica `not null` de cada una de sus columnas y `unique` del conjunto. Una restricción de clave primaria implica unicidad.

```sql
alter table emp
add email varchar(50)
constraint u_email unique;

create table dept(
    ...
    dname varchar(20) constraint nn_dname not null constraint u_dname unique,
    ...
);
```

