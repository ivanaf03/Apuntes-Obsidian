[[Bases de datos activas]]

# 1.Bases de datos activas y pasivas
Las bases de datos pasivas son simples almacenes de datos. Hoy en día apenas existen. 

## 1.1.Bases de datos activas
Las bases de datos activas realizan controles con restricciones y reaccionan ante eventos como cambios en los datos.

Las ventajas de esto son:
+ [p] *Control de restricciones:* validaciones de DNI, salario, etc. o reglas como que un empleado no gane más que su jefe.
+ [p] *Actualización de datos:* generación de claves primarias, campos autoactualizados, etc.
+ [p] *Acciones externas a la base de datos:* alertas, como un stock mínimo de un producto.

$\space$
Estas actividades se suelen implementar con triggers.

# 2.Actividades sin triggers
## 2.1.Restricciones
Las restricciones del estándar son:
+ [>] *Not null:* no permite nulos.
+ [>] *Unique y Primary key:*  garantizan la unicidad. En caso de primary key también evita nulos.
+ [>] *Check:* verifica la validez de los valores mediante una condición.
+ [>] *Foreign key:*  establece una relación entre dos tablas.

```sql
create table emp(
empno numeric(3) not null,
ename char(20) not null,
email char(25) not null constraint u_email unique,
mgr numeric(3),
deptno numeric(3),
sal numeric(7,2),
constraint pk_emp primary key(empno),
constraint fk_emp foreign key(mgr)
references emp(empno) on delete cascade on update cascade,
constraint c_sal_pos check(sal > 0) deferrable initially deferred);
```

### 2.1.1.Consideraciones
Debemos tener en cuenta que:
+ [>] La acción por defecto es abortar.
+ [>] Solo se puede hacer check a nivel de fila.
+ [>] No afectan a borrados de filas excepto `Foreign key`.
+ [>] Se pueden aplazar hasta el final de la transacción.

## 2.2.Afirmaciones
Las afirmaciones o assertions son restricciones adicionales que se pueden aplicar a una base de datos para garantizar la integridad de los datos. Funcionan como condiciones que deben cumplirse en todo momento, y si alguna de estas condiciones no se cumple, se produce una violación de la afirmación y la operación que desencadenó la violación puede ser rechazada.

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

Por defecto siempre abortan. Los SGBD no las implementan.