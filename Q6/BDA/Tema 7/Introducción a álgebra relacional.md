[[Tema 7-Optimización]]
$\space$
## 1.Consultas
En los SGBD las consultas se escriben en SQL, un lenguaje declarativo. Se indica que datos se quieren obtener, pero no como obtenerlos.

Para ello existen varias formas llamadas estrategias o planes de ejecución. Lo importante es que sean lo más eficientes posibles.
$\space$
### 1.1.Optimizador de consultas
El optimizador de consultas es un componente del SGBD que se encarga de generar el plan de ejecución de la forma más eficiente posible. 

A veces la estrategia óptima puede ser más costosa que la propia consulta. Por tanto, se determina por heurísticas cuales serían los planes más eficientes y baratos.
