[[Tema 5-Bases de datos activas]]
$\space$
## 1.Tipos de bases de datos
Las bases de datos pasivas son simples almacenes de datos. Hoy en día apenas existen. 
$\space$
### 1.1.Bases de datos activas
Las bases de datos activas realizan controles con restricciones y reaccionan ante eventos como cambios en los datos. Se implementan mediante triggers.
$\space$
#### 1.1.1.Ventajas
Las ventajas de las bases de datos activas son:
+ [p] **Control de restricciones:** validaciones de DNI, sueldo, etc. o reglas del dominio.
+ [p] **Actualización de datos:** generación de claves primarias, campos autoactualizables, etc.
+ [p] **Acciones externas a la base de datos:** alertas, como la llegada al stock mínimo.
$\space$
## 2.Actividades sin triggers
Hay cosas que no necesitan triggers para poder hacerse.
$\space$
### 2.1.Restricciones
Las restricciones reaccionan ante operaciones DML. Por ejemplo:

```sql
create table emp (
  empno number(3) not null primary key,
  ename char(20) not null,
  email char(25) not null unique constraint u_email,
  mgr number(3),
  deptno number(3),
  sal number(7,2) constraint c_sal_pos check (sal > 0) deferrable initially deferred,
  constraint fk_emp foreign key (mgr) references emp(empno)
  on delete cascade
  on update cascade
);
```

No permite hacer:

```sql
insert into emp (empno, ename, email, mgr, deptno, sal)
values (123, 'John Doe', 'invalid_email', 999, 10, -500);
-- Email inválido, no existe ese mánager, salario negativo
```
$\space$
### 2.2.Assertions
Los gestores no las implementan. Son restricciones adicionales que se pueden aplicar a una base de datos para garantizar la integridad de los datos. Funcionan como condiciones que deben cumplirse en todo momento, y si alguna de estas condiciones no se cumple, se produce una violación de la afirmación y la operación que desencadenó la violación puede ser rechazada. Por ejemplo:

```sql
create assertion <nome> check <condicion>;

create assertion as_salarios_similares
check( ( (select max(sal) from emp)-
(select min(sal) from emp) ) <100);

create assertion deptos_pequenos
check (not exists
(select deptno from emp
group by deptno
having count(*)>10));
```

