[[Tema 3-Integridad]]
$\space$
## 1.Oracle
Oracle no implementa dominios. Permite el modo aplazado siguiendo el estándar.

Permite las restricciones:
+ Primary key
+ Not null
+ Unique
+ Foreign key / References
+ Check
$\space$
### 1.1.Activación y comprobación
Oracle permite tener activadas o deshabilitadas las restricciones y también comprobar las filas ya existentes o no. Se puede especificar al crear la tabla o con `alter table`.

```sql
alter table <tabla> modify constraint <nombre_restr> { enabled | disabled }
{ validate | novalidate };

alter table <tabla> { enable | disable } constraint <nombre_restr>;
```
$\space$
### 1.2.Claves foráneas
No permite el uso de `match`. Funciona por defecto con `match simple`. 

Para las actualizaciones solo permite por defecto `no action`. Para los borrados permite `on delete cascade` y `on delete set null`.
$\space$
## 2.PostgreSQL
PostgreSQL implementa dominios. Permite el modo aplazado pero sin `check` y sin `not null`. Además si en una transacción falla una sentencia aunque esté la restricción en modo inmediato y se haga un commit, hará un rollback igual. Se puede evitar mediante savepoints.

Permite las restricciones:
+ Primary key
+ Not null
+ Unique
+ Foreign key / References
+ Check
+ Exclude
$\space$
### 2.1.Activación y comprobación
No permite activar y desactivar restricciones. Siempre comprueba las filas existentes al crear la restricción.
$\space$
### 2.2.Claves foráneas
Por defecto las claves foráneas actúan como `match simple`. Además existe `match full`, pero no `match partial`.

Permite todas las acciones referenciales del estándar.