[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## Introducción
Los documentos XML se apoyan en 2 ideas:
+ Tiene que estar bien formado, es decir, estar construido en base a las normas XML
+ Aunque es opcional, el conjunto de elementos y atributos, junto a sus restricciones, pueden estar descritas formalmente en algún tipo de esquema para comprobar que el documento sea válido.

Gracias a ello es posible construir parsers genéricos que comprueban que el documento está bien formado y válido.

#### Tipos de parsers
###### Tipo DOM (Document Object Model)
Construyen un árbol en memoria basado en el documento XML. Son muy sencillos de utilizar y permiten crear y modificar el XML a partir de él. El principal problema es la cantidad de eso de memoria en documentos XML grandes.

###### Tipo streaming
Procesan secuencialmente el código en bloques. Consumen mucha menos memoria, pero no tienen soporte para generar XML y son más difíciles de usar.

## Parsers en Java
#### SAX

#### DOM

#### JDOM

