[[Interfaces Persoa Máquina]]

## Dispositivos móviles
Se usan diferentes dispositivos para navegar en la web. Hoy en día es muy frecuente utilizar los dispositivos móviles. Las visitas a páginas web cada vez son menos frecuentes desde dispositivos de sobremesa.

## Diferencias entre móviles y ordenadores
### Pantalla
En diferentes pantallas varía el tamaño y la orientación. Se debe adaptar el contenido en consecuencia. Se puede configurar:
+ **Configuración en el cliente:** mediante cookies.
+ **Configuración en el servidor:** mime-types o redirecciones.
+ **Mobile detection con user-agent:** el user agent es un string que se envía desde un navegador web o una aplicación a un servidor web durante una solicitud. Esta cadena de texto identifica al cliente (ya sea un navegador web, una aplicación móvil u otro agente de usuario) y proporciona información sobre su sistema operativo, tipo de dispositivo, versión del software, entre otros detalles. Hoy en día está obsoleto.

### Interacción
En los dispositivos de sobremesa se interactúa generalmente con teclado y ratón, mientras que en los móviles se hace de forma táctil.

En los dispositivos táctiles los botones deben ser grandes. Los eventos son diferentes, por ejemplo "tab" en móvil o "on mouse over" en los ordenadores. Los formularios deben ser verticales, lo más simples posibles y hay que utilizar los tipos más adecuados en los campos, por ejemplo, para activar el teclado numérico para introducir un PIN.

### Conexión
En ordenador solemos conectarnos por ethernet o wifi, mientras que en móvil con wifi o datos. 

Tenemos que hacer que la página cargue lo más rápido posible. Para ello se deben minimizar los tamaños eliminando espacios, no cargar recursos no usados, comprimir las imágenes lo máximo posible y usar versiones minimizadas de librerías. Algo muy frecuente e importante es hacer un lazy loading con peticiones AJAX, es decir, bajo demanda.

### Hardware
Varían la capacidad de procesado y la alimentación. Se debe reducir el consumo de CPU para reducir el consumo de batería. Lo más importante es hacer un código simple. 

Además, es más eficiente reduciendo el número de peticiones HTTP posibles, por ejemplo, al tener todo el CSS en una hoja de estilos o al meter todos los iconos en una sola imagen e ir separándolos mediante CSS. Tampoco debemos abusar de sombras, gradientes... 

En javascript debemos usar librerías mobile, evitar diálogos, evitar malas prácticas como variables globales y concentrar cambios DOM (modificaciones que se realizan en la estructura y contenido de un documento HTML o XML a través de scripts).

### Sensores
Por ejemplo, la geolocalización se puede conseguir de muchísimos modos diferentes. Se usa el estándar W3C (navigator.geolocation). Es un protocolo asíncrono, es decir, las operaciones no bloquean la ejecución del código.

## Responsive web design
A la hora de adaptar los contenidos de un sitio web a distintos dispositivos debemos utilizar el mismo HTML para todos. Las adaptaciones a dispositivos concretos se hace en hojas de estilo CSS.

### Viewport y media queries
El viewport es todo el área visible de una página web. Depende del dispositivo. Sin configuraciones en las hojas de estilo el html se adapta al ancho de este. Se añade en el head del HTML. 

Para establecer el tamaño del viewport al tamaño de la página del dispositivo, sin escalar, evitando el zoom automático:
```
<meta name="viewport" content="width=device -width, initial-scale=1.0"/>
```

Debemos evitar hacer zoom y scroll horizontal en la página para mejorar la experiencia de usuario:
+ No debemos definir elementos con ancho fijo muy grande.
+ El contenido no puede depender de un ancho concreto de viewport.
+ Se deben usar media queries de CSS para aplicar estilos según el tamaño, que son una característica que permite aplicar estilos diferentes a un documento HTML en función de ciertos criterios, como el tamaño de la pantalla, la resolución del dispositivo, la orientación, entre otros. Por ejemplo:
```
<link rel="stylesheet" type="text/css" href="file.css" media="mediatype and|not|only (media feature)"/>
@media (media type) and|not|only (media feature) {...}

/* Media type: screen, print... */

/* 
Media feature:
	max-device-width/min-device-width
	max-width/min-width
	orientation
	aspect-ratio
	min-device-pixel-ratio/max-device-pixel-ratio
	resolution/min-resolution/max-resolution
*/
```

```
/* Estilos predeterminados para todas las pantallas */
body {
    background-color: blue;
    color: white;
}

/* Media query para pantallas más estrechas que 600px */
@media screen and (max-width: 600px) {
    body {
        background-color: red;
    }
}

/* Media query para pantallas más anchas que 600px */
@media screen and (min-width: 601px) {
    body {
        background-color: green;
    }
}
```

## Tipos de input en HTML5
```
<section>
    <h2>input type</h2>
    <input type="text" placeholder="text" /> <br />
    <input type="number" placeholder="number" /> <br />
	<input type="tel" placeholder="telephone" /> <br />
	<input type="email" placeholder="email" /> <br />
    <input type="url" placeholder="url" /> <br />
    <input type="password" placeholder="password" /> <br />
    <input type="search" placeholder="search" /> <br />
    <input type="date" /> <br />
    <input type="time" /> <br />
</section>
```