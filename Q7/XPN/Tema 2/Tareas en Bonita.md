[[Tema 2-Automatización de procesos]]

## Ejemplo de recogida de paquetes en casa
Una empresa ofrece servicios de recogida de paquetes para evitar tener que llevarlos a la oficina, vienen a recogerlo directamente a casa. El proceso comienza cuando el cliente registra los datos del pedido. El sistema calcula el coste del pedido: si pesa menos de 4kg, el coste son 5 euros si el envío es regular y 10 si es urgente. A partir de los 4 kg, se suman 2 euros al precio por cada kg adicional. Si es un paquete frágil, se aplica un recargo del 20% sobre el precio original. Una vez calculado el precio, se le muestra al cliente para que lo confirme o lo rechace. Si se rechaza, el proceso finaliza. Si se acepta, se envía un mensaje a la API REST del sistema de logística de la empresa.

![[ejemplo_tareas_bonita.png]]

## Tareas en bonita
Las tareas que soporta Bonita son:
+ Humanas
+ Servicio
+ Script
+ Envío
+ Recepción
+ Call activity (para subprocesos)

### Tareas de tipo humano
Permiten recoger datos de un formulario y almacenarlos a nivel de proceso o en la base de datos. Es obligatorio que haya entrada de datos por parte del usuario, pero permiten ejecutar operaciones como si fueran tareas de tipo script o servicio. Pueden usarse tanto los propios formularios de bonita como formularios externos. También tienen conectores de entrada y salida.

Están formadas por el contrato y el formulario. En el contrato se definen los campos de entrada del formulario a los que el usuario tiene que dar un valor. A esos campos se les pueden añadir restricciones. También pueden sacarse de las variables de negocio, no tienen por que ser totalmente nuevos.

### Tareas de tipo servicio
Son tareas que no implican interacción humana. Pueden invocar código Java , pueden ejecutar código Groovy, realizar consultas a base de datos y obtener o enviar datos mediante los conectores de entrada y salida. Se suelen utilizar para interactuar con elementos externos, como APIs o la base de datos.

### Tareas de tipo script
Permiten ejecutar operaciones simples. Se suelen utilizar para la implementación de pequeños scripts Groovy. Groovy es un lenguaje que corre en la JVM que tiene una sintaxis similar a Python.

``` Groovy
// Hola mundo
println "Hello, world!"

// Variables
def a = 1;
def b = new java.util.Date()
def c = -3.25
def d = false
def e = "Groovy!"

// Listas
def techs = []
techs.add("C") // ["C"]
techs << "C++" // ["C", "C++"]
techs.addAll(["Python", "Java"]) // ["C", "C++", "Python", "Java"]
techs.remove("Python") // ["C", "C++", "Java"]
techs = techs - "Java" // ["C", "C++"]
techs.each { println "Technology: $it"} // output: "Technology: C", "Technology: C++"
techs.eachWithIndex { it, i -> println "$i: $it"} // output: "0: C", "1: C++"
techs.contains("C") // True
isContained = "Groovy" in techs // False
techs.containsAll(["C", "C++"]) // True
techs.sort() // ["C", "C++"]
techs.sort(false) // ["C", "C++"], pero no modifica la lista original
Collections.replaceAll(techs, "C", "Ruby") // ["Ruby", "C++"]
Collections.shuffle(techs, new Random()) // ["C++", "Ruby"] o ["Ruby", "C++"]
techs.clear() // []

// Mapas
def devMap = [:]
devMap = [
    'name'      : 'Roberto',
    'framework' : 'Grails',
    'language'  : 'Groovy'
]
devMap.put('lastName', 'Perez')
devMap.each { println "$it.key: $it.value" }  
	// name: Roberto
	// framework: Grails
	// language: Groovy
	// lastName: Perez
devMap.eachWithIndex { it, i -> println "$i: $it" } 
	// 0: name=Roberto
	// 1: framework=Grails
	// 2: language=Groovy
	// 3: lastName=Perez
devMap.containsKey('name') // True
devMap.containsValue('Roberto') // True
println devMap.keySet() // [name, framework, language, lastName]
println devMap.values() // [Roberto, Grails, Groovy, Perez]

// Clases (por defecto clase pública, atributos privados y getter y setter públicos)
class Customer {
	String name
	String surname
	String email
}

// Condicionales
def x = 3
if (x == 1) {
	println("One")
} else if (x == 2) {
	println("Two")
} else {
	println("Three")
}

// Operador ternario
def y = 10
def x = (y > 1) ? "yes" : "no"

// Bucle simple
def x = 0
for (i in 0..30) {
	x += i
}

// Iterar sobre listas
def x = 0
for (i in [1,2,3]) {
	x += i
}

// Iterar sobre arrays
def numbers = (0..20).toArray()
def x = 0
for (i in numbers) {
	x += i
}

// Iterar sobre mapas
def map = [
    'name'      : 'Roberto',
    'framework' : 'Grails',
    'language'  : 'Groovy'
]
def x = ""
for ( e in map) {
	x += e.value += " "
}

// Operador para todo
def techs = ["Java", "Pyhon", "C"]
techs*.toUpperCase()

// Closures (procedimientos)

def formatToLowerCaseClosure = { 
	name -> return name.toLowerCase() 
}
formatToLowerCaseClosure("Manuel")
```

Por ejemplo, para la tarea "Calcular precio" de antes se puede crear un script:

```Groovy
Double precio = 0;

if (pedido.isUrgente()) {
	precio += 10;
} else {
	precio += 5;
}

precio += (pedido.getPeso() - 5) * 2;

if (pedido.isFragil()) {
	precio *= 1.2;
}

precio = precio.round(2);

return precio;
```

## Conectores de tareas
> [!abstract] Definición de conector
> Un conector de una tarea es bonita es la parte encargada de la emisión o recepción de datos. Puede ser de entrada o de salida.

Todas las tareas de Bonita pueden tener conectores de entrada y salida. Se suelen configurar mediante un wizzard y permiten tanto modificar los datos mediante código Groovy como con operaciones Java de las librerías importadas.

### Listado de conectores
Las tareas de Bonita se pueden conectar con:
+ Sistemas de Información Empresarial:
	+ Gestores de contenidos
	+ Enterprise Resource Planning
	+ Customer Relationship Management
+ Bases de datos o servicios de directorio LDAP
+ Sistemas de reporting
+ Sistemas de calendario
+ Servicios REST y SOAP
+ Servicios SMTP
+ Redes sociales

### Conexión a API REST
En el ejemplo anterior, la tarea "Enviar notificación a sistema logísitico" tiene un conector de salida con una llamada a una API REST en Java. El conector hace una petición POST para crear el envío.

La API podría estar implementada de esta forma:

```Java
@RestController
@RequestMapping("/logistics")
public class LogisticsController {

    private static final Logger logger = LoggerFactory.getLogger(LogisticsController.class);

    @PostMapping("/createshipment")
    public Shipment createshipment(@Valid @RequestBody ShipmentRequest request) {
        logger.info("New shipment request received: Source: {}, Destination: {}, Weight: {}",
                    request.getSource(), request.getDestination(), request.getWeight());

        Shipment shipment = new Shipment(new Random().nextLong(), "Confirmed");
        return shipment;
    }
}
```