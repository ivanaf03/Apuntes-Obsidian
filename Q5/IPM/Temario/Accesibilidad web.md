[[Interfaces Persoa Máquina]]

## WCAG
Las Web Content Accessibility Guidelines son un conjunto de pautas desarrolladas por el World Wide Web Consortium (W3C) con el objetivo de hacer que el contenido web sea más accesible para personas con discapacidades. El estándar actual es el WCAG 2.2, pero ya se está trabajando en el 3. Se divide en niveles:
+ A: Esencial
+ AA: Soporte ideal (recomendado)
+ AAA: Casos especializados

Los contenidos web deben ser:
+ **Perceptibles:** consiste en proporcionar alternativas de texto para vídeos, imágenes, etc; proporcionar alternativas a medios dependientes del tiempo como vídeos o audios, presentar contenidos en diferentes formas y facilitar la visualización de estos.
+ **Operables:** crear webs accesibles sin ratón, proporcionar tiempo suficiente para leer, diseñar contenidos que eviten por ejemplo epilepsia, proporcionar ayudas como volver atrás, o facilitar entradas a través de métodos que no sean teclado, como gestos.
+ **Entendibles:** consiste en hacer contenidos legibles y entendibles, hacer que la apariencia sea predecible, es decir, similares a páginas que ya existen y ayudar a los usuarios a corregir errores.
+ **Robustos:** maximizar la compatibilidad con los navegadores.

## Sección 508
Son una serie de disposiciones mantenidas o utilizadas por el gobierno federal de los Estados Unidos que establecen estándares y pautas para garantizar que las personas con discapacidades tengan acceso y utilidad equivalentes a la información y datos que proporciona el gobierno federal a través de tecnologías de la información.

### Requisitos
+ **Técnicos:** la codificación de la página web debe ser compatible con tecnologías asistidas.
+ **Funcionales:** el sistema tiene que ser usable por personas con discapacidad.
+ **Soporte:** la documentación tiene soporte e información alternativa.

### Imágenes y tablas
No se deben incluir imágenes relevantes como backgound-images. Todo contenido no textual debe tener una alternativa. Por ejemplo:
```
<img src="imagen.jpg" alt="Descripción de la imagen">
```


En HTML el atributo "alt" se utiliza para proporcionar un texto alternativo que describe el contenido de la imagen. La etiqueta "caption" se utiliza para proporcionar un título o una descripción breve de la tabla.
```
<img src="logo.png" alt="Logo empresa" />
<table>
<caption>Titulo de la tabla</caption>
...
</table>
```

Se puede usar WAI-ARIA con el rol "presentation" para descripciones más largas y para marcar imágenes decorativas (aquellas que no aportan información significativa al contenido).
```
<img src="decorative-image.png" alt="" role="presentation" />
```

### Contenidos repetitivos
El contenido principal sea fácilmente accesible sin tener que atravesar secciones repetitivas en cada página del sitio web.
```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Sitio Web</title>
</head>
<body>

<!-- Método para saltar el menú repetitivo -->
<a href="#contenido-principal" class="skip-link">Saltar al contenido principal</a>

<!-- Menú de navegación repetitivo -->
<nav>
    <ul>
        <li><a href="pagina1.html">Página 1</a></li>
        <li><a href="pagina2.html">Página 2</a></li>
        <li><a href="pagina3.html">Página 3</a></li>
        <!-- Más elementos de menú... -->
    </ul>
</nav>

<!-- Contenido principal -->
<section id="contenido-principal">
    <h1>Página Principal</h1>
    <p>Contenido interesante de la página principal.</p>
    <!-- Más contenido... -->
</section>

</body>
</html>
```

### Colores
La información no puede depender del color. Hay que usar colores que contrasten bien entre el fondo y el primer plano. Por tanto, no debemos, entre muchas otras cosas:
+ Usar colores para marcar acciones.
+ Indicar errores marcando bordes en rojo.
+ No marcar campos obligatorios en un formulario pintándolos de un color.

### Formularios
Los formularios deben:
+ Evitar cambios de contexto inesperados en una aplicación o sitio web cuando un usuario selecciona o introduce información, especialmente al interactuar con botones o enlaces.
+ Incluir etiquetas descriptivas o instrucciones claras junto a los campos de entrada en formularios.
+ Cuando se produce un error, proporcionar a los usuarios información clara sobre la naturaleza del error, así como sugerencias para corregirlo.

Con HTML semántico:
- "fieldset" se utiliza para agrupar elementos relacionados en un formulario.
- "legend" proporciona un título descriptivo para el grupo de elementos en el "fieldset".
- "label" se utiliza para etiquetar un campo de entrada y mejorar la accesibilidad.
```
<form>
  <fieldset>
    <legend>Your Name</legend>

    <label for="title">Title (optional)</label>
    <input id="title" type="text">

    <label for="first-name">First name*</label>
    <input id="first-name" name="first-name" type="text">

    <label for="last-name">Last name*</label>
    <input id="last-name" name="last-name" type="text">
  </fieldset>
</form>
```

Con WAI-ARIA:
Cuando las instrucciones no están cerca de los campos o no son visibles en la página, se puede utilizar WAI-ARIA para proporcionar información adicional a los usuarios que utilizan tecnologías de asistencia. Se pueden usar los atributos ARIA "aria-describedby" o "aria-label" para asociar descripciones o etiquetas adicionales a los campos.
```
<form>
  <fieldset aria-describedby="name-instructions">
    <legend>Your Name</legend>

    <label for="first-name">First name*</label>
    <input id="first-name" name="first-name" type="text" aria-describedby="first-name-instructions">
  </fieldset>

  <!-- Descripciones ocultas visualmente -->
  <div id="name-instructions" style="display: none;">Please enter your name.</div>
  <div id="first-name-instructions" style="display: none;">Enter your first name.</div>
</form>
```

### Enlaces y botones
Es esencial que el texto del enlace o botón proporcione una indicación clara del destino o la acción que se llevará a cabo al interactuar con él. Para ello debemos:
+ Evitar enlaces y botones de pulsa aquí y ver más. La forma correcta sería:
```
<!-- Enlace descriptivo -->
<a href="pagina.html">Ir a la página principal</a>

<!-- Botón con texto descriptivo -->
<button onclick="mostrarMasContenido()">Mostrar detalles</button>
```
+ No usar el mismo texto para varios enlaces o botones. La forma correcta sería:
```
<!-- Texto único y descriptivo para cada enlace -->
<a href="pagina1.html">Leer más sobre Producto A</a>
<a href="pagina2.html">Leer más sobre Producto B</a>
```
+ El destino de cada enlace o botón se debe indicar. La forma correcta sería:
```
<!-- Indicar claramente el destino -->
<a href="pagina.html">Ir a la página principal</a>

<!-- Proporcionar información clara sobre la acción -->
<button onclick="realizarAccion()">Enviar formulario</button>
```

### Teclado y focus
Todas las funcionalidades deben ser operables mediante un teclado. Los elementos HTML nativos, como botones y enlaces, generalmente tienen características de accesibilidad integradas. No debes eliminar estas características al personalizar o estilizar los elementos. Cuando se crean elementos personalizados que no son nativos de HTML, como botones personalizados o componentes interactivos, es crucial utilizar WAI-ARIA y JavaScript para proporcionar información adicional sobre la accesibilidad y replicar el comportamiento esperado.

Cuando un usuario navega utilizando el teclado, es necesario que haya un indicador visual que destaque el elemento que tiene el foco. Cuando hay un orden lógico en la navegación, como en formularios o en componentes interactivos, los elementos que reciben el foco mediante la navegación con el teclado deben seguir ese orden. La propiedad "tabindex" se utiliza para determinar el orden en el que los elementos reciben el foco cuando se navega utilizando la tecla Tab. Asignar "tabindex=0" a un elemento específico lo incluye en el flujo natural de tabulación, asegurándote de que sea accesible mediante el teclado. Esto es útil para elementos que no son botones o enlaces, pero que aún deben ser interactivos.

### Hoja de estilos
La información, estructura y relaciones entre los elementos de la página deben ser determinadas programáticamente, es decir, la estructura y la información en la página deben ser definidas de manera que las tecnologías de asistencia puedan interpretar y presentar la información de manera significativa. Esto se hace con HTML semántico.

Para ello debemos evitar usar "before" y "after" en CSS, ya que esto da cierta información y esta siempre debe estar en el HTML. 

Además hay que evitar los posicionamientos absolutos en CSS. Es una técnica en CSS que se utiliza para colocar un elemento en relación con su contenedor más cercano que puede desvincular los elementos de su flujo natural en el documento.

### Títulos y cabeceras
Toda página web debe tener un título descriptivo.
```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Título HTML</title>
</head>
```

Para estructurar los contenidos se utilizan las cabeceras (h1, h2, ...h6). Es importante no saltarse ningún nivel. Si se desea otro tamaño de cabecera se modifica en el CSS.

### Elementos multimedia
Para contenidos de audio, es importante proporcionar una transcripción textual del contenido hablado. Cuando un video no incluye sonido o tiene un contenido relevante solo en audio, es crucial proporcionar una transcripción textual o una pista de sonido alternativa. Si contienen diálogo o información audible, se deben proporcionar subtítulos.

Cuando el contenido multimedia, como audio o video, se inicia automáticamente al cargar una página, es esencial proporcionar un mecanismo para que los usuarios puedan detener o pausar ese contenido. Cuando se incluyen subtítulos o descripciones de audio, es importante proporcionar mecanismos para que los usuarios controlen su visibilidad o audición.

### Otros
Se deben evitar elementos en la página que tengan movimientos, desplazamientos, parpadeos o destellos excesivos es esencial para reducir el riesgo de provocar molestias o problemas de accesibilidad, especialmente para personas con sensibilidades visuales.

Los CAPTCHAs basados solo en imágenes pueden ser inaccesibles para lectores de pantalla. Se deben utilizar alternativas como CAPTCHAs auditivos o basados en texto.

Para mejorar la accesibilidad y la experiencia del usuario, es importante indicar el idioma general de la página y, si hay secciones específicas que cambian de idioma, proporcionar información sobre el idioma de esas secciones. Por ejemplo:
```
<!DOCTYPE html>
<html lang="en">
...
<body>
  <section lang="es">
    <!-- Contenido en español -->
  </section>
</body>
</html>
```

### Validación del HTML
+ Toolbars.
+ Pruebas en navegador sin CSS y JS.
+ pruebas en navegador de solo texto.
+ Navegar sin ratón.
+ Tecnologías asistivas, como lectores de pantalla.