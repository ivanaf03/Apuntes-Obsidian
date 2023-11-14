[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## ¿Qué es JSON?
JSON son las siglas de JavaScript Object Notation. Permite, el igual que XML, expresar información estructurada y fácilmente parseable. Se basa en structs y arrays.

## Información en JSON
#### Ejemplo
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

#### Documento JSON
Es una secuencia de caracteres que contiene texto en formato JSON. Se dice que está bien formado si cumple con un conjunto de reglas, al igual que en XML. Distingue entre mayúsculas y minúsculas.

Contienen valores, que puede ser de uno de los siguientes tipos:
+ object
+ array
+ string
+ number
+ boolean
+ null

En JSON no hay comentarios, atributos ni espacio de nombres. Los objetos y arrays solo tienen nombre si no son el valor de un campo de un objeto.

## Validación de documentos JSON
Los esquemas JSON sirven para expresar restricciones sobre el contenido de un documento JSON. 

#### Ejemplos
| **Documento JSON**    | **Schema JSON**                                        |
|-------------------|---------------------------------------------------|
| null              | {"type": "null"}                                  |
| true              | {"type": "boolean"}                               |
| 123               | {"type": "integer", "minimum": 100}              |
| "2023-10-26"      | {"type": "string", "format": "date"}             |
| \["hola", "adios"] | {"type" : "array", "items" : {"type" : "string", "minLength" : 4}, "minItems" : 1}
| {"nombre": "Juan", "edad": 30} | {"type": "object", "properties": {"nombre": {"type": "string"}, "edad": {"type": "integer"}}, "required": ["nombre", "edad"]}
| "activo" | {"type": "string", "enum": \["activo", "inactivo", "pendiente"]}
