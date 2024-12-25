[[Tema 3-SOA y BPM]]

## Qué es SOA?
> [!abstract] Definición de SOA
> SOA son las siglas de Service Oriented Architecture. Es un estilo de diseño de software en el que las aplicaciones están compuestas por servicios independientes y reutilizables que se comunican entre sí a través de interfaces bien definidas. Cada servicio realiza una función específica y puede ser utilizado por diferentes aplicaciones o sistemas.

SOA es un paradigma que engloba el diseño, la gestión y las tecnologías. El objetivo es dar soporte a los procesos de negocio de la organización combinando las diferentes funcionalidades de los servicios de la arquitectura.

### Pilares de SOA
Esta arquitectura se compone de:
+ **Servicios:** funcionalidades de negocio.
+ **Infraestructura:** hardware y software que permiten combinar los servicios de forma sencilla. Se suelen usar middlewares.
+ **Políticas y procesos:** normas que gestionan el conjunto de sistemas distribuidos con diferentes propietarios.

> [!abstract] Definición de middleware
> Un middleware es un software que actúa como intermediario entre diferentes aplicaciones, sistemas o componentes, facilitando la comunicación y gestión de datos entre ellos. 

### Implementación de una SOA
No se suele partir de 0 para crear una SOA. Se parte de una arquitectura de un Sistema de Información que va evolucionando con el tiempo para dar respuesta al modelo de negocio y a la operativa de la organización. ´´

## Servicios en SOA
> [!abstract] Definición de servicio
> Un servicio es una unidad de funcionalidad independiente y autónoma que realiza una tarea específica, accesible a través de una interfaz bien definida.

### Características de los servicios
Los servicios deben:
+ **Representar una funcionalidad de negocio:** deben ser concretos, específicos y autocontenidos. Suelen ser conjuntos de funcionalidades muy relacionadas.
+ **Tener una interfaz:** la interfaz tiene que ser siempre la misma independientemente de que varíe la implementación para ser tolerantes al cambio.
+ **Ser definidos por contrato:** un ejemplo de contrato puede ser: nombre, entradas, salidas y excepciones. A mayores puede incluir precondiciones y postcondiciones y requisitos no funcionales.

Una buena forma de definir los servicios es mediante un diseño API first con archivos YAML. Por ejemplo:

```json
openapi: 3.0.0
info:
  title: Servicio de Gestión de Pedidos
  version: 1.0.0

paths:
  /crear:
    post:
      summary: Crear un pedido
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                usuarioId:
                  type: string
                productos:
                  type: array
                  items:
                    type: object
                    properties:
                      productoId:
                        type: string
                      cantidad:
                        type: integer
                direccionEnvio:
                  type: string
                metodoPago:
                  type: string
              required: [usuarioId, productos, direccionEnvio, metodoPago]
      responses:
        '201':
          description: Pedido creado con éxito.
        '400':
          description: Solicitud inválida.

  /{pedidoId}:
    get:
      summary: Consultar un pedido
      parameters:
        - name: pedidoId
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Información del pedido.
        '404':
          description: Pedido no encontrado.
```

### Tipos de servicios
Los servicios pueden ser:
+ **Básicos:** utilizan directamente datos o lógica básica para implementar funcionalidades simples.
+ **Compuestos:** combinan varios servicios básicos para implementar funcionalidades más complejas.
+ **De proceso:** implementan un proceso de negocio complejo a partir de la orquestación de otros servicios.
+ **Microservicios:** están altamente especializados, son autónomos e implementan funcionalidades específicas de manera aislada.

## Acoplamiento entre servicios
> [!abstract] Definición de acoplamiento
> El acoplamiento es el grado de dependencia o interacción entre diferentes módulos, componentes o clases de un sistema. Un acoplamiento bajo significa que los módulos son independientes entre sí, lo que facilita el mantenimiento, la reutilización y la flexibilidad del sistema. Un acoplamiento alto indica que los módulos están fuertemente dependientes, lo que puede dificultar la modificación o expansión del sistema sin afectar otras partes.

| **Característica**                 | **Acoplamiento fuerte**                  | **Acoplamiento débil**                     |
| ---------------------------------- | ---------------------------------------- | ------------------------------------------ |
| *Conexiones físicas*               | Punto a punto                            | A través de un mediador                    |
| *Estilo de comunicación*           | Sincrónica                               | Asincrónica                                |
| *Modelo de datos*                  | Tipos complejos comunes                  | Solo tipos simples y comunes               |
| *Sistema de tipos*                 | Fuerte                                   | Débil                                      |
| *Patrón de interacción*            | Navegar por árboles de objetos complejos | Mensajes autocontenidos centrados en datos |
| *Control de la lógica de procesos* | Control centralizado                     | Control distribuido                        |
| *Vinculación*                      | Estática                                 | Dinámica                                   |
| *Plataforma*                       | Fuerte dependencia de la plataforma      | Independiente de la plataforma             |
| *Transaccionalidad*                | 2PC (compromiso en dos fases)            | Compensación                               |
| *Despliegue*                       | Simultáneo                               | En diferentes momentos                     |
| *Versionado*                       | Actualizaciones explícitas               | Actualizaciones implícitas                 |

### Conexión punto a punto vs. conexión a través de mediador
La conexión punto a punto se basa en que las aplicaciones o sistemas se comunican directamente entre sí, sin un intermediario. Cada sistema o servicio necesita conocer la ubicación y las interfaces de los demás sistemas con los que interactúa. 

En cambio, al realizar conexión a través de un mediador, como puede ser un ESB (Enterprise Service Bus) se realizan conexiones punto a punto, pero pasando por el mediador. Por ejemplo, el servicio A le hace una petición al mediador, el mediador se la hace a B, B le responde y le devuelve la respuesta a A.

Para optimizar esto se puede utilizar un Publisher. Funciona de forma similar al patrón observador o al productor-consumidor. El servicio A es un publisher y publica la información en el ESB, que tiene unos suscriptores con reglas definidas. Por ejemplo, B puede estar suscrito y cuando ve la publicación en el ESB actúa. El ESB es el observador y el Publisher el observable.

### Ventajas de los mediadores
Utilizar un mediador como un ESB permite:
+ Tener conectividad entre los servicios.
+ Transformar datos.
+ Enrutamiento inteligente.
+ Seguridad.
+ Fiabilidad.
+ Gestionar los servicios.
+ Monitorización.

### Comunicación y conexión con el mediador
La comunicación síncrona se basa en la espera de respuestas mediante un timeout. Si se utiliza un middleware, se pueden implementar políticas de reintentos. Aporta tolerancia a fallos y gestión de prioridades.

En cambio, la comunicación asíncrona permite evitar que el comunicador espere de forma activa una respuesta. Los ESB permiten implementar comunicación asíncrona.

Para comunicarse con el ESB se pueden hacer:
+ **Conexiones basadas en protocolos:** utilizan protocolos estándar como SOAP para enviar datos e invocar el servicio web alojado en el ESB.
+ **Conexiones basadas en APIs:** utilizan APIs soportadas por algunos lenguajes para interactuar directamente con el ESB.