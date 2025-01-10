[[Tema 6-Validación automática]]

## Técnicas de preparación de datos
Las técnicas de preparación de datos son:
+ **Particiones equivalentes:** se dividen los rangos de las entradas y salidas que deben recibir o devolver la misma respuesta. Por cada rango, se elige un valor cualquiera como representante para la prueba. 
+ **Valores frontera:** es una técnica complementaria a las particiones equivalentes que consiste en coger los valores que quedan en las fronteras entre las particiones.
+ **Selección de datos aleatorios:** es otra técnica que complementa la técnica de las particiones equivalentes introduciendo aletoriedad.

## Otras técnicas de prueba
Otras técnicas que permiten probar el código son:
+ **Mutación de código:** consiste en alterar el código fuente simulando fallos comunes como limites de comparaciones en condiciones y bucles, uso de valores constantes, etc. La idea es que si un test no detecta el cambio en el mutante, el test se considera débil y necesita ser mejorado.
+ **Inserción de fallos:** consiste en modificar el código introduciendo errores de lógica o de procesamiento para ver la robustez del software ante estos cambios.
+ **Revisiones:** pueden hacerse por un experto o hacer una peer review, lo que ayuda a mejorar la calidad del código y encontrar errores.

## Calidad de las pruebas
Para medir la calidad de un software se puede medir la cobertura que este tiene mediante las pruebas:
+ **Cobertura de instrucciones:** evalúa si se ha pasado por cada instrucción al menos una vez en las pruebas.
+ **Cobertura de decisiones:** evalúa si se ha pasado al menos una vez por cada decisión posible en los condicionales. La cobertura de instrucciones no comprueba que se pase por más de una rama.
+ **Cobertura de condiciones:** evalúa si, en cada rama de decisión, se ha pasado al menos una vez por cada posible combinación de todas las combinaciones posibles que esta tiene.

### Métricas de calidad y efectividad de las pruebas
Para saber como de efectivas son las pruebas se pueden definir métricas:
+ **De proceso:** cantidad de bugs en producción, cantidad de bugs por cantidad de modificaciones, etc.
+ **De usabilidad:** facilidad de uso, ratio de productividad, etc.