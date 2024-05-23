[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.Concurrencia en sistemas multiusuario
Los SGBD son multiusuario normalmente y permiten el acceso concurrente a datos. Puede haber varias transacciones accediendo a los mismos datos a la vez o en instantes de tiempo muy próximos.
$\space$
### 1.1.Transacciones
Los SGBD controlan la concurrencia mediante transacciones. Las transacciones deben cumplir las propiedades ACID (Atomicity, Consistency, Isolation, Durability).
$\space$
### 1.2.Técnicas de concurrencia
El control de concurrencia se puede hacer mediante ciertas técnicas:
+ Técnicas de bloqueo.
+ Técnicas basadas en marcas de tiempo.
+ Control multiversión.