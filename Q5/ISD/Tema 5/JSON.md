[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## ¿Qué es JSON?
JSON son las siglas de JavaScript Object Notation. Permite, al igual que XML, expresar información estructurada y fácilmente parseable. Se basa en structs y arrays.

### Documento JSON
Es una secuencia de caracteres que contiene texto en formato JSON. Se dice que está bien formado si cumple con un conjunto de reglas, al igual que en XML. Distingue entre mayúsculas y minúsculas. Por ejemplo:
```
[
	{
	"movieId": 3,
	"title": "Dark Knight Rises Again",
	"runtime": 165,
	"releaseDate": { "day": 20, "month": 7, "year": 2012 },
	"directors": [ "Cristopher Nolan" ],
	"actors": [ "Christian Bale", "Morgan Freeman" ],
	"genres": [ "THR" ],
	"price": 4.99,
	"description": "Ocho años después de los acontecimientos de The Dark Knight, Gotham se encuentra en un estado de paz. En virtud de los poderes otorgados por la Ley Dent, el comisario Gordon casi ha erradicado la violencia y el crimen organizado. Sin embargo, todavía se siente culpable por el encubrimiento de los crímenes de Harvey Dent."
	},
	{
	"movieId": 4,
	"title": "Con la Muerte en los Talones",
	"runtime": 136,
	"releaseDate": { "day": 26, "month": 9, "year": 1959 },
	"directors": [ "Alfred Hitchcock" ],
	"actors": [ "Cary Grant", "Eve Marie Saint", "James Manson" ], 
	"genres": [ "THR", "COM" ], "price": 3.99,
	"description": "Roger O. Thornhill (Cary Grant) es un ejecutivo publicitario de Nueva York al que unos espías confunden con un agente del gobierno. Debe escapar, pero lo siguen de cerca. Durante la fuga conoce a una atractiva mujer, Eve Kendall (Eva Marie Saint), que lo ayuda." 
	} 
]
```

Contienen valores, que pueden ser: object, array, string, number, boolean o null.

En JSON no hay comentarios, atributos ni espacio de nombres. Los objetos y arrays solo tienen nombre si no son el valor de un campo de un objeto. En XML no se podía saber se había un array de un solo elemento, en cambio en JSON sí.

## Validación de documentos JSON
Los esquemas JSON sirven para expresar restricciones sobre el contenido de un documento JSON. Pasa igual que en XML, un JSON que cumpla las restricciones de un esquema es válido y una aplicación que parsea JSON comprueba que está bien formado, pero no si es válido siempre. No existe un estándar para obtener esquemas JSON.

## Esquemas JSON
Un esquema JSON contiene un objeto con campos que imponen un conjunto de restricciones. Es más simple es ({}); cualquier JSON es válido con este esquema.

### Campos descriptivos
+ **$schema:** Indica que el documento JSON es un esquema y su versión. No es obligatorio.
+ **$id:** asigna un valor único al esquema. Tampoco es obligatorio.
+ **$comment:** permite añadir comentarios.

### Ejemplos
| **Documento JSON**    | **JSON Schema**                                        |
|-------------------|---------------------------------------------------|
| null              | {"type": "null"}                                  |
| true              | {"type": "boolean"}                               |
| 123               | {"type": "integer", "minimum": 100}              |
| "2023-10-26"      | {"type": "string", "format": "date"}             |
| \["hola", "adios"] | {"type" : "array", "items" : {"type" : "string", "minLength" : 4}, "minItems" : 1}
| {"nombre": "Juan", "edad": 30} | {"type": "object", "properties": {"nombre": {"type": "string"}, "edad": {"type": "integer"}}, "required": ["nombre", "edad"]}
| "activo" | {"type": "string", "enum": \["activo", "inactivo", "pendiente"]}