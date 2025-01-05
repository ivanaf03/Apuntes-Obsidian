[[Tema 7-Test project]]

## Ciclo de vida de pruebas en .NET
Al inicio de una ejecución de pruebas, se crea una instancia con `unit test runner`. Esto crea una sesión de test llamada test fixture que obtiene los atributos de test. Después, crea un test context, que es una instancia que dura todo lo que dura la sesión de testing. Luego se llaman los métodos que inicializan el assembly y la clase (`AssemblyInitialize` y `ClassInitialize`).

Para cada método de test, se recupera un test fixture, se llama al método anotado con `TestInitialize` y se invoca. Finalmente, se llama al método anotado con `TestCleanup`.

Una vez ejecutados los test, se llama a `classCleanup` y a `assemblyCleanup`. 

Si durante cualquier momento del ciclo de vida se produce una excepción, el test termina con un fallo. 

## Cómo deben ser las pruebas?
Las pruebas unitarias deben ser:
+ **Automáticas:** no deben requerir configuración adicional mientras se ejecutan.
+ **Completas:** cubren toda la funcionalidad, incluso los métodos privados y protegidos a los que llama.
+ **Repetibles:** si tienen los mismos datos, deben devolver los mismos resultados.
+ **Independientes:** los resultados de unos test de afectan a los demás.
+ **Eficientes:** deben ser suficientemente eficientes para soportar múltiples ejecuciones simultáneas.