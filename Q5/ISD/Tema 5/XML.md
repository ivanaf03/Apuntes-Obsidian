[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

### ¿Qué es XML?
Es un lenguaje de tags similar a HTML. XML impone una serie de normas sobre el uso de tags:
+ Siempre se abren y se cierran
+ Todos los documentos tienen un tag raíz
+ Pueden tener atributos

Sirve para expresar información estructurada y parseable.

### Formato de un documento XML
Un documento XML es una secuencia de caracteres que contiene texto en dicho formato. Una aplicación XML es un conjunto particular de tags que permite representar información.

Se dice que un XML está bien formado si cumple con el conjunto de reglas que se expone. Además distingue mayúsculas y minúsculas. Los comentarios se escriben así:
```
<!-- comentario -->
```

##### Declaración XML
Tiene que aparecer al principio del documento y no es obligatoria. Indica la versión de XML y la codificación de caracteres. Por ejemplo:
```
<?xml version="1.0" encoding="UTF-8"?>
```

##### Elementos y atributos
+ Todos los documentos deben tener un elemento raíz. Por ejemplo \<movies>.
+ Un tag puede tener atributos. Estos van entrecomillados con comillas dobles o simples.
+ El elemento vacío es otra notación, pero sin elementos anidados ni texto. Puede tener atributos. Por ejemplo: 
```
<tag-1 attr-1="val1" attr-2="val2"></tag-1>
<!-- Por comodidad, se suele representar como: -->
<tag-1 attr-1="val1" attr-2="val2"/>
```