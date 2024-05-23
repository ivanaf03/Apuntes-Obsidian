[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.Qué es el esquema multiversión?
Consiste en mantener varias versiones del mismo dato para mejorar la concurrencia. Evita  las esperas en las lecturas. Se debe elegir la versión apropiada.

Cuando una transacción escribe un dato  por primera vez crea una versión de este. Cada versión contiene el valor del dato, la marca de tiempo para lectura y la marca de tiempo para escritura.

![[multiversion.png]]

La lectura siempre se puede hacer. la versión correcta es aquella con la ME más grande que sea menor o igual que la marca de transacción.

La escritura comprueba que no se lea en una transacción futura y crea una nueva versión del dato.
$\space$
### 1.1.Ejemplo

![[multiversion ejemplo.png]]