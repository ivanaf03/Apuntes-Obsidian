[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## ¿Qué es XML?
Es un lenguaje de tags similar a HTML. XML impone una serie de normas sobre el uso de tags:
+ Siempre se abren y se cierran
+ Todos los documentos tienen un tag raíz
+ Pueden tener atributos

Sirve para expresar información estructurada y parseable.

## Formato de un documento XML
Un documento XML es una secuencia de caracteres que contiene texto en dicho formato. Una aplicación XML es un conjunto particular de tags que permite representar información.

Se dice que un XML está bien formado si cumple con el conjunto de reglas que se expone. Además distingue mayúsculas y minúsculas. Los comentarios se escriben así:
```
<!-- comentario -->
```

#### Ejemplo
```
 <?xml version="1.0" encoding="UTF-8"?>
 <movies>
	<!–- Dark Knight Rises Again. -->
	<movie>
		<movieId>3</movieId>
		<title>Dark Knight Rises Again</title>
		<runtime>165</runtime> 
		<releaseDate day="20" month="7" year="2012"/>
		<director>Cristopher Nolan</director>
		<actor>Christian Bale </actor>
		<actor>Morgan Freeman</actor>
		<genre>THR</genre>
		<price>4.99</price>
		<description> Ocho años después de los acontecimientos de The Dark Knight, Gotham se encuentra en un estado de paz. En virtud de los poderes otorgados por la Ley Dent, el comisario Gordon casi ha erradicado la violencia y el crimen organizado. Sin embargo, todavía se siente culpable por el encubrimiento de los crímenes de Harvey Dent.</description>
	</movie>
	<!–- Con la Muerte en los Talones. -->
	<movie>
		<movieId>4</movieId>
		<title>Con la Muerte en los Talones</title>
		<runtime>136</runtime> 
		<releaseDate day="26" month="9" year="1959"/>
		<director>Alfred Hitchcock</director>
		<actor>Cary Grant</actor>
		<actor>Eve Marie Saint</actor>
		<actor>James Manson</actor>
		<genre>THR</genre>
		<genre>COM</genre>
		<price>3.99</price>
		<description> Roger O. Thornhill (Cary Grant) es un ejecutivo publicitario de Nueva York al que unos espías confunden con un agente del gobierno. Debe escapar, pero lo siguen de cerca. Durante la fuga conoce a una atractiva mujer, Eve Kendall (Eva Marie Saint), que lo ayuda. Algunas de sus escenas son recordadas por la magnitud de las imágenes: la persecución de Thornhill por un campo sembrado por una avioneta que quiere matarlo, una pelea en el Monte Rushmore y la escena filmada de incógnito en la sede de la ONU </description>
	</movie>
 </movies>
```

#### Declaración XML
Tiene que aparecer al principio del documento y no es obligatoria. Indica la versión de XML y la codificación de caracteres. Por ejemplo:
```
<?xml version="1.0" encoding="UTF-8"?>
```

#### Elementos y atributos
+ Todos los documentos deben tener un elemento raíz. Por ejemplo \<movies>.
+ Un tag puede tener atributos. Estos van entrecomillados con comillas dobles o simples.
+ El elemento vacío es otra notación, pero sin elementos anidados ni texto. Puede tener atributos también Por ejemplo: 
```
<tag-1 attr-1="val1" attr-2="val2"></tag-1>
<!-- Por comodidad, se suele representar como: -->
<tag-1 attr-1="val1" attr-2="val2"/>
```
+ Estas dos notaciones serían equivalentes:
```
<movie>
	<actor>C. Bale</actor>
	<actor>M. Freeman</actor>
</movie>
```
```
<movie>
	<actor name="C. Bale"/>
	<actor name="M. Freeman"/>
</movie>
```

#### Caracteres especiales
| Referencia   | Carácter  |
| ------------ | --------- |
| &lt;        | <         |
| &amp;       | &         |
| &gt;        | >         |
| &quot;      | "         |
| &apos;      | '         |

## Espacio de nombres
Es un mecanismo que se utiliza para evitar conflictos de nombres cuando se emplean elementos y atributos con etiquetas personalizadas en un documento XML. El propósito principal de los espacios de nombres es permitir que diferentes vocabularios o estándares XML coexistan en un mismo documento sin ambigüedades o conflictos de nomenclatura.

Los espacios de nombres se identifican mediante URIs (Identificadores Uniformes de Recursos) que pueden ser URLs o cualquier otra cadena que proporcione un identificador único. Cada elemento y atributo en un documento XML puede estar asociado con un espacio de nombres, y esto se logra utilizando un prefijo para indicar a qué espacio de nombres pertenece un elemento o atributo. Por ejemplo:
```
<libro xmlns="http://www.ejemplo.com/libros">
  <titulo>XML y sus aplicaciones</titulo>
  <autor>Jane Doe</autor>
</libro>
```

Es común utilizar un prefijo para los elementos y atributos dentro del espacio de nombres. Por ejemplo:
```
<libro:libro xmlns:libro="http://www.ejemplo.com/libros">
  <libro:titulo>XML y sus aplicaciones</libro:titulo>
  <libro:autor>Jane Doe</libro:autor>
</libro:libro>
```

