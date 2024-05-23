[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.En qué consisten los bloqueos?
Una transacción debe bloquear un dato antes de poder acceder a él. Se pueden hacer tres operaciones de bloqueo:
+ **S(A):** bloqueo shared sobre A.
+ **X(A):** bloqueo exclusive sobre A.
+ **U(A):** desbloqueo sobre A.

![[bloqueos operaciones.png]]
$\space$
### 1.1.Reglas de funcionamiento
Las operaciones de bloqueo se basan en:
+ Antes de leer un dato hay que conseguir un bloqueo shared.
+ Antes de escribir un dato hay que conseguir un bloqueo exclusive sobre él.
+ Si una transacción no puede conseguir un bloqueo se quedará en espera.
$\space$
### 1.2.Conversión de bloqueos
Dentro de una transacción un bloqueo puede:
+ **Promocionar un bloqueo:** pasa de compartido a exclusivo.
+ **Degradar un bloqueo:** pasa de exclusivo a compartido.
$\space$
## 2.Protocolo de bloqueo en 2 fases
Consiste en 2 fases:
+ **Adquisición:** una transacción solo puede adquirir nuevos bloqueos o promocionar los ya conseguidos.
+ **Liberación:** una transacción libera un bloqueo. A partir de ahí solo puede liberar o degradar los ya existentes.
$\space$
### 2.1.Características y variantes
Si todas las transacciones lo implementan, entonces la planificación es serializable por conflictos. 

Por ejemplo:

![[2pl blqoueo.png]]

![[2pl 2.png]]
$\space$
#### 2.1.1.Variantes
Para eliminar el problema de las anulaciones en cascada existen 2 variantes:
+ **2PL riguroso:** las transacciones no liberan los bloqueos exclusivos hasta confirmarse o anularse.
+ **2PL estricto:** las transacciones no liberan ningún bloqueo hasta que se confirman o anulan.
$\space$
## 3.Interbloqueos
Ocurren cuando dos transacciones se quedan en espera, esperando a que la otra libere un bloqueo para continuar.

![[Imágenes/interbloqueo.png]]

![[interbloqueo2.png]]
$\space$
### 3.1.Técnicas de prevención
Consiste en evitar que se produzca un interbloqueo. Son pesimistas, es decir, pueden anular transacciones cuando podría ocurrir que no hubiera interbloqueo.

Se le da a cada transacción una marca temporal cuando inicia.  Se usa en 2PL, cuando una transacción aborta libera sus bloqueos. 

Puede hacerse:
+ **Esperar-morir:** Si M(T1) es menor que M(T2), T1 espera. Sino aborta y se reinicia con la misma marca de tiempo.
+ **Herir-esperar:** Si M(T1) es menor que M(T2), T2 aborta y se reinicia con la misma marca de tiempo. Sino T1 espera.
$\space$
#### 3.1.1.Ejemplo esperar-morir
Suponemos que las marcas de tiempo son i para cada Ti.

| T1   | T2               |
| ---- | ---------------- |
| W(A) | -                |
| -    | W(B)             |
| -    | W(A) -- rollback |
| W(B) | -                |

| T1             | T2              |
| -------------- | --------------- |
| -              | W(A)            |
| W(B)           | -               |
| W(A) -- espera | -               |
| -              | W(B) --rollback |
$\space$
#### 3.1.1.Ejemplo herir-esperar
Suponemos que las marcas de tiempo son i para cada Ti.

| T1               | T2              |
| ---------------- | --------------- |
| W(A)             | -               |
| -                | W(B)            |
| -                | W(A)  -- espera |
| W(B) -- rollback | -               |

| T1                | T2   |
| ----------------- | ---- |
| -                 | W(A) |
| W(B)              | -    |
| W(A)  -- rollback | -    |
| -                 | W(B) |
$\space$
### 3.2.Técnicas de detección
Los gestores generalmente implementan técnicas de detección. Siguen un enfoque optimista. 

Utilizan un grafo con esperas. Los nodos son las transacciones y las aristas las dependencias o esperas.

Si hay un ciclo en el grafo se produciría interbloqueo.

![[grafo interbloqueo.png]]

La solución es deshacer la transacción que produce el interbloqueo.