[[Tema 6-Nuget]]

## Añadir paquetes externos
Normalmente, cuando queremos añadir algo externo a una aplicación, recurrimos a Google. Se busca la versión compatible, lo cuál ya es un problema, se descarga y descomprime y se añade al proyecto y se configura. Es mucho más complejo de lo que puede parecer, ya que pueden surgir dependencias con otros paquetes o incompatibilidades.

### Añadir paquetes mediante Nuget
Nuget es un gestor de paquetes. Localiza los paquetes en repositorios locales o en la web y se encarga de gestionar las dependencias.

Descarga en el directorio `packages` y comprueba que todas las descargas se hayan completado. Después crea o actualiza el `packages.config` donde indica las dependencias del proyecto. Modifica el fichero de configuración del proyecto también.

Se puede compartir el directorio `packages` entre diferentes soluciones configurando el fichero `nuget.config`.