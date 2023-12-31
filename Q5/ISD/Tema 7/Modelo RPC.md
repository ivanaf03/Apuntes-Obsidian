[[Tema 7-Diseño e implementación de Servicios RPC]]

## El modelo RPC
Remote Procedure Call es un modelo donde un proceso expone su funcionalidad como una serie de operaciones que pueden ser invocados desde cualquier aplicación en cualquier punto de la red. El objetivo es que el programador invoque con la misma facilidad una operación de una aplicación que una función de una librería. Se basa en la generación automática de código de creación y parseo.

### Funcionamiento
El programador del servidor modela un conjunto de operaciones que pueden ser invocadas por los clientes. Se definen en un fichero especial, que contiene:
+ Nombre de la operación.
+ Nombre y tipo de los parámetros de entrada.
+ Nombre y tipo de los parámetros de salida.

Después ejecuta un compilador especial del framework y genera el esqueleto. Este contiene:
+ Código fuente plantilla.
+ Librerías que se ocupan de la comunicación con los clientes.

El programador del cliente también compila el fichero de definición y genera un stub. El stub ofrece al programador del cliente operaciones con la misma firma que las indicadas en el fichero de definición Cada operación del stub, al ser invocada, se ocupa de los detalles de invocar la operación correspondiente en el servicio y obtener la respuesta. Invoca las operaciones del stub para programar el cliente.

Existe un compilador del framework RPC para cada lenguaje de programación soportado. Cada compilador genera los stubs y los skeletons usando la sintaxis y tipos de datos del lenguaje objetivo para que el cliente y servidor puedan estar escritos en lenguajes diferentes.

### Flujo de una aplicación remota
1. La aplicación cliente invoca una operación del stub pasándole los parámetros necesarios.
2. El stub genera un mensaje encapsulando el nombre de la operación y los parámetros de entrada recibidos, envía el mensaje por la red al servidor y espera la respuesta.
3. El esqueleto, cuando recibe el mensaje del stub, comprueba en el mensaje qué operación se desea invocar, extrae los parámetros de entrada, e invoca la operación correspondiente del código fuente plantilla o de la implementación de la interfaz.
4. La implementación del código fuente plantilla o de la interfaz convierte los parámetros recibidos a los tipos adecuados, por ejemplo, para invocar una operación de una capa modelo.
5. La operación de la capa modelo se ejecuta y devuelve un resultado.
6. La implementación del código fuente plantilla o de la interfaz convierte el resultado de la capa modelo a los tipos con los que trabajan esas operaciones y lo devuelve.
7. El esqueleto genera un mensaje encapsulando el resultado recibido y envía el mensaje por la red al cliente.
8. El stub al recibir la respuesta del servidor, extrae de la misma el resultado y se lo devuelve al cliente.
9. El programa cliente recibe la respuesta a su invocación y continua su ejecución.

### Ventajas
+ Uso muy intuitivo para un programador.
+ Transparencia de la red para los programadores.

### Inconvenientes
+ En algunas implementaciones alto acoplamiento cliente-servidor.
+ Cambios en la interfaz obligan a regenerar el stub.
+ El servidor puede ser una aplicación autónoma que no está bajo nuestro control.

Estos problemas ya no existen en las implementaciones modernas.
