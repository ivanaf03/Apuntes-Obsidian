[[Tema 6-Validación automática]]

## Development testing
Para diseñar las pruebas de desarrollo, debe planearse al menos realizar una prueba por requisito, por cada funcionalidad y por sus posibles combinaciones y una prueba por cada método. Se pueden hacer las pruebas de diferentes formas.

> [!abstract] Definición de Behaviour-driven development
> Es una técnica de programación que se basa en hacer las pruebas tras hacer la parte del código que se va a probar.

> [!abstract] Definición de Test-driven development
> Es una técnica de programación que se basa en hacer las pruebas antes de hacer la parte que se va a codificar.

![[pruebas_development.png]]

El development testing está formado por:
+ Pruebas unitarias.
+ Pruebas de integración.
+ Pruebas de sistema.

### Pruebas unitarias
Para cubrir completamente una unidad de programación se deben probar todas las operaciones públicas y probar todas las combinaciones de estados posibles. Se suele seguir el estándar xUnit, que divide las pruebas en setup, invocaciones y aserciones. Si falla la prueba, se considera exitosa.

En el setup se debe mockear todo lo que no pertenezca a la unidad que se va a probar.

### Pruebas de integración
En un sistema software, las unidades cooperan para formar sistemas más complejos. Cada componente ofrece una interfaz o API pública para interactuar con los demás. Las pruebas de integración consisten en probar las interacciones de las interfaces, asumiendo que todas las unidades funcionan correctamente.

Se busca encontrar errores de sintaxis, de semántica o de sincronía entre interfaces.

### Pruebas de sistema
Son pruebas de integración, pero probadas sobre una versión completa del sistema. Se incluyen los componentes o librerías externos al equipo y se realizan pruebas con estas incorporadas y, a mayores, se hacen pruebas no funcionales. Estas deben basarse lo máximo posible al entorno de producción real.

Se configura el entorno, se diseñan las pruebas de estrés, de rendimiento, de carga y de usabilidad necesarias y se realizan.

## User testing
Son las pruebas de aceptación. Se utilizan los escenarios de prueba de sistema más relevantes como base para hacer una demostración al usuario de la aplicación que se va a desplegar. Esto se conoce como release testing. 

Es recomendable que las realice el propio usuario. Para ello sigue historias de usuario o diagramas de secuencia simples.

![[prueba_aceptación.png]]

## Clasificación de las pruebas
Las pruebas pueden ser:
+ **Estáticas, dinámicas o simbólicas:** depende de si necesitan que el software esté en ejecución o no (o se simule).
+ **Caja blanca o caja negra:** depende de si necesitan conocer la estructura interna del código o no.
+ **Positivas o negativas:** depende de si buscan o no ejecutar el software en condiciones normales de uso.

Otra clasificación complementaria es:
+ **Funcionales:** comprueban que el software haga lo qué tiene que hacer. Suelen ser dinámicas de caja negra.
+ **Estructurales:** comprueban la calidad interna del software. Suelen ser pruebas de caja blanca.
+ **No funcionales:** miden el rendimiento del software. Suelen ser dinámicas de caja negra. 