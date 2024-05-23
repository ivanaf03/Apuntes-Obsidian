[[Tema 9-Concurrencia en bases de datos]]
$\space$
## 1.Tipos de marcas de tiempo
Para las técnicas anteriores son necesarias varias marcas de tiempo. La transacción más reciente no es la última transacción que realiza una acción, sino la que tiene la MT más alta:
+ **M(Ti):** marca de tiempo de la transacción, como el de las técnicas de prevención.
+ **ML:** marca de la transacción más reciente que leyó un dato.
+ **ME:** lo mismo pero para escritura.
$\space$
### 1.1.Ejemplos

![[ML.png]]

![[problemas planificación.png]]
$\space$
### 1.2.Ordenamiento básico por marcas de tiempo

![[marcas tiempo ordenamiento.png]]
$\space$
### 1.3.Ordenamiento estricto por marcas de tiempo
El ordenamiento básico no evita el problema de anulación en cascada ni las planificaciones no recuperables. 

![[ordenamiento estricto.png]]

Consiste en que si Ti solicita una operación sobre un dato A, con MTi > ME (A) siendo ME(A)=MTk, Ti espera a que acabe Tk.

En el caso anterior T2 espera a que acabe T1 antes de hacer lectura y escritura sobre A.
$\space$
### 1.4.Regla de Thomas
Es una variante del ordenamiento básico. Implementa seriabilidad por vistas, pero no por conflictos. Solo aplica cuando hay escrituras a ciegas:

![[algoritmo Thomas.png]]

La diferencia ocurre cuando se quiere escribir un dato que fue escrito por una transacción posterior. La escritura es obsoleta y no se hace.

![[ejemplo thomas.png]]