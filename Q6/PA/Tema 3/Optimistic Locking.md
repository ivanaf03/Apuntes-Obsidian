[[Tema 3-Capa lógica de negocio con Spring]]
$\space$
## 1.Problema de la seriabilidad
Cuando hay mucha carga no es viable utilizar siempre un nivel de aislamiento `SERIALIZABLE`. Es recomendable que sea `READ_COMMITED`. Si es mayor que este último, habrá demasiados bloqueos en las filas afectadas por una transacción para garantizar aislamiento.

Hibernate para ello asume que siempre se trabaja con un nivel de aislamiento menor a `READ_COMMITED`.
$\space$
### 1.1.Consecuencias de utilizar niveles inferiores
Como consecuencia de tener un nivel de aislamiento menor a `READ_COMMITED`, pueden darse:
+ **Phantom reads:** ocurren cuando una transacción realiza una consulta en la base de datos, luego otra transacción inserta o elimina filas relevantes para esa consulta, y finalmente la primera transacción ejecuta la misma consulta nuevamente, obteniendo resultados diferentes.
+ **Non repeteable reads:** se produce cuando una transacción realiza una consulta en la base de datos y, antes de que finalice, otra transacción modifica o elimina las filas relevantes para esa consulta, lo que provoca que la primera transacción obtenga diferentes resultados si ejecuta la misma consulta nuevamente.
+ **Second lost update:** sucede cuando dos transacciones leen los mismos datos, realizan cambios y luego intentan escribir esos cambios en la base de datos. Si la segunda transacción sobrescribe los cambios realizados por la primera antes de que la primera transacción haya confirmado sus cambios, se produce una pérdida de la actualización realizada por la primera transacción. Es lo más común.
$\space$
#### 1.1.1.Problema del second lost update
Partimos de un servicio que tiene un método que permite añadir dinero a una cuenta bancaria:

```java@Transactional
public class AccountServiceImpl implements AccountService {
    ...
    
    @Override
    public void add(Long accountId, BigDecimal amount) throws InstanceNotFoundException {
        Account account = findAccount(accountId);
        account.add(amount);
    }
}
```

Dos empleados de un banco van a añadir dinero a la cuenta a la vez.:

```
T1 -- lee cuenta, balance=1000
T2 -- lee cuenta, balance=1000

T1 -- account.add(100), balance=1100
T2 -- account.add(200). balance=1200

T1 -- commit, balance=1100 en BD
T2 -- commit, balance=1200 en BD  # sobreescribe el valor de T1 (second lost update)
```
$\space$
## 2.Optimistic locking
En el optimistic locking, en lugar de bloquear los recursos de forma exclusiva mientras se realiza una operación, se permite que múltiples transacciones accedan y modifiquen los datos al mismo tiempo. Sin embargo, antes de confirmar los cambios, el sistema verifica si otros usuarios han modificado los mismos datos.

Permite evitar los problemas de second lost update en un nivel de aislamiento `READ_COMMITED`. En JPA se puede hacer añadiendo un atributo numérico anotado con  `@Version` y añadiendo a la tabla correspondiente ese mismo atributo.

El valor lo proporciona el propio mapeador objeto-relacional. Cuando se hace una inserción de una entidad se le da el valor 0. Cada vez que se actualiza una instancia de la entidad se incrementa el valor de la versión en 1 mediante la consulta:

```sql
update Table
set <<columns>>, version=version+1
where id=table_id and version=version (en memoria);
```

Internamente `PreparedStatement.executeUpdate` devuelve el número de filas afectadas por la consulta. Si esto devuelve 0 filas, o sea, que no coincide el número de versión, se lanza una `RuntimeException` y se hace el rollback.
$\space$
### 2.1.Ejemplo

```
T1 -- lee cuenta, balance=1000, versión=10
T2 -- lee cuenta, balance=1000, version=10

T1 -- account.add(100), balance=1100, version=10
T2 -- account.add(200). balance=1200, version=10

T1 -- update account set balance=1100, version=version+1 where id=1 and version=10
T1 -- commit, balance=1100 en BD, version=11 en BD

T2 -- update account set balance=1200, version=version+1 where id=1 and version=10
T2 -- 0 rows: RuntimeException
T2 -- rollback
```
$\space$
### 2.2.Ventajas
+ [p] La estrategia es escalable porque no se realizan bloqueos sobre las filas que se leen en la transacción.
+ [p] La excepción puede subir a capas superiores e informar al usuario de que no se ejecutó su operación.