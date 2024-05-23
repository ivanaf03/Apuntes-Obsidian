[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.Planes de ejecución
Un plan de ejecución entre varias transacciones es una ordenación de las escrituras y lecturas de forma que se mantenga su orden dentro de cada transacción. Para cada transacción, si una operación va antes de otra, en el plan final también debe ir.

Puede ser:
+ **En serie:** las operaciones se ejecutan todas de forma consecutiva, sin intercalar con otras transacciones. Siempre producen resultados correctos.
+ **No en serie:** pueden producir planes incorrectos, pero si son correctos aumentan el grado de concurrencia.

![[concurrencia bbdd.png]]
$\space$
### 1.1.Conflictos
Dos acciones entran en conflicto si son de transacciones diferentes, al menos una de ellas es de escritura y trabajan sobre el mismo dato. No son intercambiables.

![[conflictos.png]]
$\space$
### 1.2.Planes equivalentes y serializables
Dos planes son equivalentes por conflictos si, para cada par de operaciones en conflicto, el orden de estas operaciones es el mismo en ambos planes. Un plan es serializable por conflictos si es equivalente por conflictos a algún plan en serie.

![[planes en serie.png]]
$\space$
#### 1.2.1.Grafo de serialización
Cada transacción es un nodo. Se crea una arista de A a B si en A aparece antes una operación que tenga conflicto con B.

![[grafo de precedencia.png]]
$\space$$\space$
#### 1.2.2.Seriabilidad por vistas
Dos planes son equivalentes si una transacción lee el valor inicial de A en P1, también lo debe leer en P2; si la transacción que escribe el último valor es la misma; y si toda transacción que lee un valor escrito por otra en P1 también lo hace en P2.

Permite que las transacciones produzcan estados intermedios diferentes, siempre y cuando el estado final sea el mismo.

Si hay escrituras a ciegas, es decir, sin lecturas previas, puede haber planes serializables por vistas que no lo son  por conflictos.

Si suponemos que siempre se hace escritura restringida, es decir, siempre se lee antes de escribir, la seriabilidad por vistas y conflictos es idéntica.

![[serial vistas.png]]
$\space$$\space$
