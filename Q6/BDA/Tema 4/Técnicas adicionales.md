[[Tema 4-Seguridad]]
$\space$
## 1.Otras técnicas
Además del acceso obligatorio y discrecional podemos usar otras técnicas:
+ Vistas
+ Bases de datos estadísticas
+ Cifrado de información
+ Prevención de SQL injection
+ Copias de seguridad
+ Auditorías
$\space$
### 1.1.Uso de vistas
A veces se quiere limitar el acceso a ciertas filas o columnas de una tabla. Esto se puede hacer mediante vistas, ya que Oracle no soporta el `grant` de un `select`.

Además, para las filas no sería posible aunque algunos gestores soporten la posibilidad de elegir ciertas columnas.

La solución es retirar los permisos del usuario sobre una tabla, crear una vista con la consulta deseada y dar permisos sobre ella.  Por ejemplo:

```sql
create view emp20 as select empno, ename, job, mgr, hiredate, sal, comm, deptno from emp where deptno=20 with check option; 

grant all privileges on emp20 to usr;
```
$\space$
### 1.2.Bases de datos estadísticas
Las bases de datos estadísticas son bases de datos que muestran solo datos obtenidos a partir de una serie de tuplas. Por debajo si que contienen datos confidenciales, pero solo se publica la información calculada. Es una forma de anonimizar.

![[base datos estadistica.png]]

La desventaja es:
+ [c] A veces se puede llegar a los datos confidenciales a través de los calculados. Normalmente no se publican datos que no vengan de cierto número mínimo de tuplas.
$\space$
### 1.3.Cifrado de información
Las comunicaciones del cliente con el gestor deben estar cifradas. Se suelen usar SSL y TLS o certificados. También se pueden cifrar datos en base de datos, como contraseñas o información sensible.
$\space$
#### 1.3.1.Mecanismos de cifrado
Se puede hacer:
+ Cifrar de forma externa y guardar solo la clave.
+ Usar cifrado bidireccional, por ejemplo, para recuperar datos de un historial médico.
$\space$
### 1.4.Prevención de inyección SQL
Las inyecciones SQL son problemas de seguridad que se dan cuando se controlan mal la entrada de datos en los programas que acceden a la base de datos.

Se pueden prevenir comprobando los parámetros de entrada en los programas de acceso a BBDD.
$\space$
### 1.5.Backups
Los backups son elementos de seguridad porque permiten evitar la pérdida de información. Puede darse por:
+ Borrados.
+ Errores de software.
+ Fallos hardware.