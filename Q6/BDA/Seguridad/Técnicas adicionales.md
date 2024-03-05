[[Seguridad]]

# 1.Otras técnicas
Además de los controles de acceso podemos utilizar otras técnicas que mejoren la seguridad en las bases de datos:
+ [>] Vistas
+ [>] Bases de datos estadísticas
+ [>] Cifrado de la información
+ [>] Prevención de inyección SQL
+ [>] Copias de seguridad
+ [>] Auditorías

## 1.1.Vistas
A veces se quiere limitar el acceso a ciertas filas o columnas de una tabla. No siempre es posible dar los permisos siempre sobre las tablas.

```sql
grant select(empno, ename, job, mgr, hiredate)
on emp
to usr;

-- Oracle no lo soporta, por ejemplo
```

Para las columnas algunos gestores pueden, pero para las filas no es posible.

### 1.1.1.Solución
Para poder limitar con facilidad el acceso a filas o columnas podemos retirar los permisos sobre la tabla. Crear una vista con las filas o columnas deseadas y dar permiso a la vista.

```sql
-- si usr tenía privilegios sobre emp:
revoke all privileges on emp from usr;

create view emp20
as select empno, ename, job, mgr, hiredate, sal, comm, deptno
from emp
where deptno=20
with check option;
grant all privileges on emp20 to usr;
```

## 1.2.Bases de datos estadísticas
Las bases de datos estadísticas son bases de datos que muestran solo datos obtenidos a partir de una serie de tuplas. Por debajo si que contienen datos confidenciales, pero solo se publica la información calculada. Es una forma de anonimizar.

![[base datos estadistica.png]]

La desventaja es:
+ [c] A veces se puede llegar a los datos confidenciales a través de los calculados. Normalmente no se publican datos que no vengan de cierto número mínimo de tuplas.

## 1.3.Cifrado de información
Las comunicaciones con los SGBD deben estar cifradas, sobre todo si es una conexión a través de internet. Habitualmente se usan SSL/TLS y certificados.

También se pueden cifrar los datos de la BD, ya que alguna información como contraseñas de usuarios o información confidencial no se debe saber.

### 1.3.1.Mecanismos de cifrado
Se debe proteger la información ante accesos externos:
+ [>] *Para contraseñas:* cifrar externamente la información y almacenar solo la clave cifrada. Se suele usar cifrado unidireccional, como HASH o MD5. Al hacer el `login` se cifra la clave introducida y se compara con la almacenada.
+ [>] *Para información confidencial:* se suele utilizar cifrado bidireccional para recuperar la información cifrada.

## 1.4.Prevención de inyección SQL
