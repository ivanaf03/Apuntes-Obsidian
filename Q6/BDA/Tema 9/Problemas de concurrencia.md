[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.Problemática
Existen 4 problemas relacionados con la concurrencia:
+ Actualización perdida.
+ Lectura sucia.
+ Análisis incoherente y lectura no repetible.
+ Filas fantasma.
$\space$
### 1.1.Actualización perdida
Empezamos con A=5000.

| T1           | T2           |
| ------------ | ------------ |
| Read(A, a1)  | -            |
| -            | Read(A, a2)  |
| a1=a1-300    | a2=a2+2000   |
| -            | Write(A, a2) |
| Write(A, a1) | -            |

El resultado esperado es A=5000-300+2000=6700. Sin embargo, se pierde la actualización de T2. El resultado es A=4700.
$\space$
### 1.2.Lectura sucia
Empezamos con A=5000.

| T1           | T2          |
| ------------ | ----------- |
| Read(A, a1)  | -           |
| a1=a1-300    | -           |
| Write(A, a1) | -           |
| -            | Read(A, a2) |
| -            | a2=a2+2000  |
| Rollback     | -           |

Como T1 hace rollback solo se ejecuta T2. El resultado esperado es A=5000+2000. Sin embargo, como T2 utiliza el valor A=4700 obtenido en T1 es resultado es A=5000-300+2000=6700. 

Para solucionarlo se podría hacer una anulación en cascada, haciendo también rollback de T2 al hacerlo en T1 y en todas las demás transacciones dependientes.
$\space$
#### 1.2.1.Planificación no recuperable
Puede ocurrir que T2 hace commit antes de que T2 haga rollback.

| T1           | T2          |
| ------------ | ----------- |
| Read(A, a1)  | -           |
| a1=a1-300    | -           |
| Write(A, a1) | -           |
| -            | Read(A, a2) |
| -            | a2=a2+2000  |
| -            | Commit      |
| Rollback     | -           |

No se podría hacer una anulación en cascada porque violaría las propiedades ACID. La propiedad de Durability indica que tras hacer un commit ese valor debe permanecer en BBDD.
$\space$
### 1.3.Análisis incoherente
Empezamos con A=B=C=5000.

| T1             | T2           |
| -------------- | ------------ |
| total=0        | -            |
| Read(A, a1)    | -            |
| total=total+a1 | -            |
| Read(B, b1)    | -            |
| total=total+b1 | -            |
| -              | Read(B, b2)  |
| -              | b2=b2-300    |
| -              | Write(B, b2) |
| -              | Read(C, c2)  |
| -              | c2=c2+300    |
| -              | Write(C, c2) |
| -              | Commit       |
| Read(C, c1)    | -            |
| total=total+c1 | -            |

El valor esperado de total debería ser A=5000+5000+5000=15000. Pero T2 hace un commit actualizando el valor de C (5000+300). Por tanto, el resultado es 15300.
$\space$
#### 1.3.1.Lectura no repetible
Dos lecturas en base de datos son diferentes en una misma transacción sin que se haya actualizado el dato en ella.

| T1          | T2           |
| ----------- | ------------ |
| Read(A, a1) | -            |
| -           | Read(A, a2)  |
| -           | a2=a2-500    |
| -           | Write(A, a2) |
| -           | Commit       |
| Read(A, a1) | -            |

En ambas lecturas en T1 a1 debería ser el mismo. Sin embargo, como T2 hizo commit, el valor de a1 ha disminuido en 500.
$\space$
#### 1.3.2.Filas fantasma
Es similar a la lectura no repetible. Consiste en que aparezcan nuevas filas entre dos lecturas en la misma transacción.

```sql
-- T1
select ename
from emp
where sal = 800;
-- resultado: smith

-- T2
insert into emp(empno, ename, sal)
values(1234, 'sam', 800);
commit;

-- T1
select ename
from emp
where sal = 800;
-- resultado: smith, sam
```

