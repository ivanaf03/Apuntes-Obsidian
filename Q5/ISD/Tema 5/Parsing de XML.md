[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

## Introducción
Los documentos XML se apoyan en 2 ideas:
+ Tiene que estar bien formado, es decir, estar construido en base a las normas XML
+ Aunque es opcional, el conjunto de elementos y atributos, junto a sus restricciones, pueden estar descritas formalmente en algún tipo de esquema para comprobar que el documento sea válido.

Gracias a ello es posible construir parsers genéricos que comprueban que el documento está bien formado y es válido.

## Tipos de parsers
+ **DOM:** Construyen un árbol en memoria basado en el documento XML. Son muy sencillos de utilizar y permiten crear y modificar el XML a partir de él. El principal problema es la cantidad de uso de memoria en documentos XML grandes.
+ **Streaming:** Procesan secuencialmente el código en bloques. Consumen mucha menos memoria, pero no tienen soporte para generar XML y son más difíciles de usar.

## Parsers en Java
+ **SAX (Simple API for XML):** Es un parser de tipo streaming de Java SE eficiente y basado en eventos. No tiene soporte para la generación de XML.
+ **DOM (Document Object Model):** Es un parser de tipo DOM que también forma parte de Java SE. Tiene soporte para generación de XML.
+ **JDOM:** Es una alternativa a DOM pensada para Java. 
