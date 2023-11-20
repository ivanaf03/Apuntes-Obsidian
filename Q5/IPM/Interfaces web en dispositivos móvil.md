[[Interfaces Persoa Máquina]]

## Dispositivos móviles
Se usan diferentes dispositivos para navegar en la web. Hoy en día es muy frecuente utilizar los dispositivos móviles.

##### Diferencias entre móviles y ordenadores
+ **Pantalla:** tamaño y orientación. Se debe adaptar el contenido al tamaño y orientación de la pantalla. Se puede configurar:
	+ Configurar en el cliente: mediante cookies u opciones.
	+ Configurar en el servidor: mime-types o redirecciones.
	+ Mobile detection con user-agent: string que se envía desde un navegador web o una aplicación a un servidor web durante una solicitud. Esta cadena de texto identifica al cliente (ya sea un navegador web, una aplicación móvil u otro agente de usuario) y proporciona información sobre su sistema operativo, tipo de dispositivo, versión del software, entre otros detalles.
+ **Interacción:** m&k y táctil. En los dispositivos táctiles los botones deben ser grandes. Los eventos son diferentes, por ejemplo tab en móvil o on mouse over en los ordenadores. Los formularios, por ejemplo, deben ser lo más simples posibles, utilizar los tipos más adecuados en los campos...
+ **Conexión:** en ordenador podemos conectarnos por ethernet o wifi, pero en móvil con wifi o datos. Tenemos que intentar que la página cargue rápido. Para ello se deben minimizar los tamaños eliminando espacios, no cargar recursos no usados, comprimir las imágenes lo máximo posible y usar versiones minimizadas de librerías. Algo muy importante es hacer un lazy loading con peticiones AJAX, es decir, bajo demanda.
+ **Hardware:** varían la capacidad de procesado y la alimentación. Se debe reducir el consumo de CPU para reducir el consumo de batería. Lo más importante es hacer un código simple. Además es más eficiente hacer las menores peticiones http posibles, por ejemplo, tener todo el css en una hoja de estilos o meter todos los iconos en una sola imagen e ir separándolos mediante css. Además no usar sombras, gradientes... En javascript debemos usar librerías mobile, evitar diálogos, evitar variables globales y concentrar cambios DOM.
+ **Sensores:** por ejemplo, la geolocalización. Se usa el estándar W3C (navigator.geolocation). Es un protocolo asíncrono. 

### Responsive web design
Para adaptar los contenidos del sitio web a distintos dispositivos debemos utilizar el mismo HTML para todos. Las adaptaciones a dispositivos concretos se hace en hojas de estilo CSS.

##### Viewport
Es toda el área visible de una página web. Depende del dispositivo. Sin configuraciones en las hojas de estilo el html se adapta al ancho del viewport La solución es definir en el head de html:
```
<meta name="viewport" content="width=device -width ,
initial -scale=1.0" />
# establece el tamaño del viewport al tamaño de la página del dispositivo, sin escalar
```
Debemos evitar hacer zoom y scroll horizontal en la página para mejorar la experiencia de usuario:
+ No definir elementos con ancho fijo muy grande.
+ El contenido no puede depender de un ancho concreto de viewport.
+ Utilizar media queries de css para aplicar estilos según el tamaño.
```
<link rel="stylesheet" type="text/css" href="file.css"
media="mediatype and|not|only (media feature)" />
@media mediatype and|not|only (media feature) {...}

# Media type: screen, print...
# Media feature:
	max-device-width/min-device-width
	max-width/min-width
	orientation
	aspect-ratio
	min-device-pixel-ratio/max-device-pixel-ratio
	resolution/min-resolution/max-resolution
```

### Tipos de input en HTML5
+ Text
+ Number
+ Telephone
+ Email
+ Url
+ Password
+ Search
+ Time
+ Date