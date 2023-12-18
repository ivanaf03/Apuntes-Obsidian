[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## ¿Qué es XML?
Es un lenguaje de tags similar a HTML. XML impone una serie de normas sobre el uso de tags:
+ Siempre se abren y se cierran y dentro pueden tener tags anidados.
+ Todos los documentos tienen un tag raíz.
+ Pueden tener atributos.

Sirve para expresar información estructurada y parseable.

## Formato de un documento XML
Un documento XML es una secuencia de caracteres que contiene texto en dicho formato. Una aplicación XML es un conjunto particular de tags que permite representar información.

Se dice que un XML está bien formado si cumple con el conjunto de reglas que se expone. Además, distingue mayúsculas y minúsculas.

Los comentarios se escriben así:
```
<!-- comentario -->
```

### Ejemplo
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

### Declaración XML
Tiene que aparecer al principio del documento, pero no es obligatoria. Indica la versión de XML y la codificación de caracteres. Por ejemplo:
```
<?xml version="1.0" encoding="UTF-8"?>
```

### Elementos y atributos
Todos los documentos deben tener un elemento raíz. Por ejemplo \<movies>. Un elemento o tag puede tener atributos. Estos van entrecomillados con comillas dobles o simples.

Otra notación es el elemento vacío, que no contiene elementos anidados ni texto. Puede tener atributos también Por ejemplo: 
```
<tag-1 attr-1="val1" attr-2="val2"></tag-1>
<!-- Por comodidad, se suele representar como: -->
<tag-1 attr-1="val1" attr-2="val2"/>
```

Estas dos notaciones serían equivalentes:
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

Para aumentar la claridad se suelen seguir unas convenciones, aunque no son obligatorias:
+ Usar elementos para datos multivaluados.
```
<colores> <color>Rojo</color> <color>Verde</color> <color>Azul</color> </colores>
```

+ Usar contenido de elementos para datos de gran cantidad de texto.
```
<articulo>
    <titulo>El Viaje del Héroe</titulo>
    <contenido>
        El viaje del héroe es un arquetipo narrativo que se encuentra presente en mitos y leyendas de diversas culturas a lo largo de la historia.
        ...
        (Texto extenso)
        ...
    </contenido>
</articulo>
```

+ Usar atributos o contenido de elementos en cualquier otro caso.
```
<libro id="123">
    <titulo>La Sombra del Viento</titulo>
    <autor>Carlos Ruiz Zafón</autor>
    <anoPublicacion>2001</anoPublicacion>
</libro>
```

### Caracteres especiales
| **Referencia**   | **Caracter**  |
| ------------ | --------- |
| \&lt;        | <         |
| \&amp;       | &         |
| \&gt;        | >         |
| \&quot;      | "         |
| \&apos;      | '         |

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

Otro ejemplo:
```
<?xml version="1.0" encoding="UTF-8"?>
<movies xmlns="http://ws.udc.es/movies/xml" xmlns:review="http://reviews.example.com">
   <movie>
      <movieId>3</movieId>
      <title>Dark Knight Rises Again</title>
      <runtime>103</runtime>
      <description>Ocho años después ...</description>
      <review:title>Cualquiera puede ser un héroe</review:title>
      <review:description>Es difícil hacer una crítica de una película tan compleja ...</review:description>
      <review:rating>4</review:rating>
   </movie>
</movies>
```

En este ejemplo se define el elemento raíz "movies" se especifican dos espacios de nombres. El espacio de nombres predeterminado (http://ws.udc.es/movies/xml) se aplica al elemento "movies", mientras que "review" (http://reviews.example.com) se asocia con el prefijo review y se utiliza para elementos específicos de las críticas. Conceptualmente son dos esquemas, uno que sirve para obtener información sobre las películas y otro sobre las críticas.

## Validación de documentos XML
Existen algunos tipos de esquemas para expresar que atributos y elementos son válidos en una aplicación XML y que restricciones tienen. Dos estándares utilizados son:
+ **DTD (Document Type Definition):** declaraciones que describen los elementos, los atributos y la relación entre ellos en un documento XML. Por ejemplo:
```
<!DOCTYPE library [
  <!ELEMENT library (book+)>
  <!ELEMENT book (title, author, genre, price)>
  <!ELEMENT title (#PCDATA)>
  <!ELEMENT author (#PCDATA)>
  <!ELEMENT genre (#PCDATA)>
  <!ELEMENT price (#PCDATA)>
  <!ATTLIST book id CDATA #REQUIRED>
]>
```

+ **XML Schema:** alternativa en XML más avanzada y poderosa al DTD. Por ejemplo:
```
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="library">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="book" maxOccurs="unbounded">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="title" type="xs:string"/>
              <xs:element name="author" type="xs:string"/>
              <xs:element name="genre" type="xs:string"/>
              <xs:element name="price" type="xs:decimal"/>
            </xs:sequence>
            <xs:attribute name="id" type="xs:integer" use="required"/>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Si un documento XML cumple las restricciones de los esquemas se considera válido. Cuando una aplicación parsea un XML comprueba que esté bien formado, pero no siempre que sea válido.

### XML Schema
```
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ws.udc.es/movies/xml" xmlns="http://ws.udc.es/movies/xml" elementFormDefault="qualified>
```

- **xmlns:xsd="http://www.w3.org/2001/XMLSchema":** Define el espacio de nombres XML para el propio lenguaje XML Schema. El prefijo xsd se usa como un alias para el espacio de nombres http://www.w3.org/2001/XMLSchema.
- **targetNamespace="http://ws.udc.es/movies/xml":** Especifica el espacio de nombres principal al cual pertenece este esquema. Este espacio de nombres se utilizará para calificar los elementos definidos en el esquema. En este caso, los elementos definidos pertenecen al espacio de nombres http://ws.udc.es/movies/xml.
- **xmlns="http://ws.udc.es/movies/xml":** Asigna un espacio de nombres predeterminado para los elementos del esquema. Este espacio de nombres se aplicará a los elementos sin prefijo en el documento XML. En este caso, los elementos sin prefijo se consideran parte del espacio de nombres http://ws.udc.es/movies/xml.
- **elementFormDefault="qualified":** Especifica que los elementos definidos en el esquema deben calificarse con su espacio de nombres. Esto significa que los elementos deben tener el prefijo o el atributo xmlns para indicar su pertenencia al espacio de nombres.

Los tipos de elementos o atributos pueden ser:
+ **Simples:** string, int, long, short, float, double, boolean, byte, datetime... Pueden tener asociadas restricciones, por ejemplo, el tamaño máximo de un string.
+ **Complejos:** son tipos que a su vez tienen atributos o elementos. Pueden usar compositores como sequence, que define una secuencia ordenada de elementos; all, donde los elementos pueden aparecer en cualquier orden; o choice, donde suele aparecer uno de los elementos. Los elementos se definen con su nombre, tipo y se puede indicar el número máximo y mínimo de apariciones. Por ejemplo:
```
<xsd:complexType name="ReleaseDate">
	<xsd:attribute name="day" type="xsd:short"/>
	<xsd:attribute name="month" type="xsd:short"/>
	<xsd:attribute name="year" type="xsd:short"/>
</xsd:complexType>
```