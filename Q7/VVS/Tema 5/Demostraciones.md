[[Tema 5-Cáculo de secuentes]]

## Qué es una demostración?
> [!abstract] Definición de demostración
> Una demostración es una justificación de una sentencia.

Para ello, se utilizan proposiciones que se consideran válidas, llamadas premisas.

### Utilidad de las demostraciones
Es muy complicado determinar que $\{A_1, ... A_n\}\models B$ de forma semántica. Por eso, se demuestran de forma sintáctica, es decir, $\{A_1, ... A_n\}\vdash B$, mediante reglas formales. Demostrar consiste en encontrar un procedimiento que permita verificar una argumentación paso a paso manipulando de forma válida los símbolos de las fórmulas.

Se hacen en sistemas formales, contextos donde los símbolos no tienen significado y lo único que se puede suponer es lo que dicta el sistema.

## Sistemas formales
Un sistema formal está formado por:
+ Un lenguaje formal.
+ Un conjunto de axiomas lógicos.
+ Un conjunto de reglas de inferencia.
+ Una definición de prueba o demostración.

> [!abstract] Definición de teoría
> Una teoría es un sistema formal con un conjunto $\Gamma$ de premisas o axiomas. Si este conjunto es vacío, se denomina teoría básica del sistema formal.

### Propiedades
> [!abstract] Definición de teorema de validez
> Todos los teoremas de $T[\Gamma]$ son consecuencias lógicas de $\Gamma$, es decir, si $T[\Gamma]\vdash B$ entonces $\Gamma \models B$

> [!abstract] Definición de teorema de completitud
> Dada una teoría $T[\Gamma]$, todas las consecuencias lógicas de $\Gamma$ son teoremas de $T[\Gamma]$, es decir, si $T[\Gamma]\models B$ entonces $\Gamma \vdash B$

Si el cálculo es correcto, se puede decir que es equivalente la consecuencia semántica y la sintáctica.