[[Aseguramento da calidade]]

# 1.Diseño de alto y bajo nivel
+ [!] 1 diapositiva

Aplica toda la norma para la empresa al ser una empresa de software completa. La norma dice que debemos hacer un diseño en base a los requisitos y después revisarlo.

En la especificación de requisitos hacemos la ERS y un plan de pruebas de aceptación. Esto permite al jefe de proyecto empezar a planificar. 

En empresas muy pequeñas el código cuenta como diseño. La norma dice que debemos revisar el diseño, lo que sería realizar las pruebas unitarias.

En la diapositiva tenemos que tener en cuenta que el jefe de proyecto en la fase de requisitos ha estimado el proyecto y su tamaño. Por tanto sabe si se hace diseño de alto y bajo nivel, solo alto nivel o nada. Si hacemos diseño de alto nivel debemos saber quién lo hace mediante una plantilla. Debemos también indicar quién la hace, cómo la hace, cuándo y en base a qué. Si hacemos diseño de bajo nivel alguien lo tendrá que hacer mediante una plantilla. También debemos mirar quién lo hace, cómo lo hace, cuándo y qué obtiene como resultado.

Según la estimación del proyecto, a parte de la flexibilidad de realizar o no todas las fases, debemos decidir si se realizan todos los entregables o no.

En la diapositiva debemos marcar quién hace el trabajo, que productos de entrada hay, qué plantillas utiliza, quién lo revisa, cuándo lo revisa, si hay algún procedimiento que lo guie y que productos de salida hay.

# 2.Programación
+ [!] 1 diapositiva

En las empresas suelen indicar cómo nombrar las variables, en qué orden van los campos, cómo poner los comentarios, etc. Incluso hay empresas con compiladores no compilan códigos con complejidad ciclomática muy alta.

Dada la flexibilidad del ciclo en base al tamaño del software el jefe de proyecto decide cuáles son las entradas de la fase de programación. Para saberlo se sigue el plan de proyecto.

El trabajo está sujeto a ciertas guías en nuestra empresa.

# 3.Pruebas
+ [!] 4 diapositivas: pruebas unitarias, de integración, de sistema y de aceptación.

Las pruebas de aceptación son las únicas indicadas por la ISO. La norma dice que debemos revisar todo el producto y, si encontramos errores, no debe ser entregado al cliente. Debemos saber en todo momento el estado de los productos. 

En las pruebas unitarias se coge cada módulo por separado y se comprueba si funciona. Son pruebas de caja blanca. La complejidad ciclomática permite medir cuantas pruebas debo hacer.

En las pruebas de integración se pruebas las interfaces. Una vez terminado esto se prueba el sistema al completo.

# 4.SIE
+ [!] 1 diapositiva

El SIE es el Sistema de Información de Errores. Se hace porque la norma dice que hay que asegurar que no lleguen productos no conformes al cliente. Además debemos saber en que estado de pruebas están los productos. 

No es viable recoger los errores todos que salgan de las pruebas unitarias. En las pruebas de integración tampoco es viable recoger los errores, suelen ser sencillos de arreglar. En las pruebas de sistema se detectan errores mucho más graves. Estos sí se deben recoger.

El SIE es una base de datos que recoge los errores detectados en las pruebas de sistema. Son errores muy costosos en tiempo y esfuerzo. Lo más interesante es guardar cómo se arreglaron.

Los errores de las pruebas de aceptación son muy graves. Esto incumple la ISO por todos lados. Tienen que ser registrados.

En la diapositiva debemos indicar quién tiene acceso al SIE, para qué tienen acceso y qué deben hacer. También debemos indicar qué información sale del SIE.