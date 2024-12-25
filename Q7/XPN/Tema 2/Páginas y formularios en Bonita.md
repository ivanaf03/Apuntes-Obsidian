[[Tema 2-Automatización de procesos]]

## Diseño de páginas y formularios
Bonita permite crear una interfaz web con páginas y formularios. Se realizan a partir de un conjunto de widgets. Si los widgets forman parte de un formulario deben colocarse dentro de un "Form container".

Los formularios se crear automáticamente a partir de las tareas de tipo humano. 

### Variables de los formularios
La variable `context` tiene el valor `../API/bpm/task/{{taskid}}/context`. Sirve para acceder al contexto del proceso, lo que permite acceder a las variables de proceso. Es solo de lectura y es lo que renderiza los formularios. Es un objeto JSON de este estilo:

```json
{
  "caseId": "12345",
  "processInstanceId": "67890",
  "taskId": "54321",
  "processDefinitionId": "45678",
  "variables": { 
    // Variables de proceso
    "pedido": {
	    "email": "hola@example.com",
	    "dni": "12121212A",
	    ...
    }
  }
}
```

Para acceder a estas variables se puede definir otra variable, por ejemplo, `pedido`, con el valor `../{{context.pedido_ref.link}}`. Esto facilita la sintaxis para trabajar, por ejemplo, con los campos del formulario.

Otra variable importante es `formOutput`. Contiene una expresión en JavaScript que determina que se enviará a la aplicación al pulsar el botón submit del formulario. Su valor tiene este aspecto:

```javascript
if( $data.pedido ){ 
	return { 
		pedidoInput: { 
			nombre: $data.pedido.nombre !== undefined ? $data.pedido.nombre : null,
			apellidos: $data.pedido.apellidos !== undefined ? $data.pedido.apellidos : null, 
			email: $data.pedido.email !== undefined ? $data.pedido.email : null,
			...
		} 
	}
 }
```

## Páginas
Las páginas muestran cualquier tipo de información al usuario, incluso un formulario. Para generar páginas de forma dinámica se puede usar la API de Bonita mediante expresiones JS. 

### Variables de las páginas
Para acceder a la sesión de usuario se utiliza la variable `session`, que contiene el valor `../API/system/session/unusedId`, del cual se pueden obtener atributos como el nombre o el identificador.

Para acceder al modelo se pueden definir también variables. Por ejemplo, `myPendingRequests`, que realiza el método `findByUserIdAndStatus` mediante el valor `../API/bdm/businessData/com.company.model.TravelRequest?q=findByUserIdAndStatus&p=0&c=10&f=userId={{session.user_id}}&f=status=pending`.

Para obtener las variables de un proceso se puede hacer una petición mediante la variable `processDef`, con valor `../API/bpm/process?p=0&c=1&f=name=Travel%20Request`. 
