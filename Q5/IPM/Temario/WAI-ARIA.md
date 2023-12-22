[[Interfaces Persoa Máquina]]

## ¿Qué es WAI-ARIA?
El Web Accessibility Initiative - Accessible Rich Internet Applications (WAI-ARIA) es una iniciativa del World Wide Web Consortium (W3C) que proporciona especificaciones para mejorar la accesibilidad de las aplicaciones web interactivas y dinámicas. ARIA proporciona una serie de atributos y roles adicionales que pueden ser añadidos al código HTML, especialmente cuando se utilizan tecnologías como AJAX, JavaScript y otras técnicas de desarrollo web avanzadas.

Se suele utilizar en:
+ Controles interactivos, como menús, sliders, pop-ups...
+ Regiones dinámicas.
+ Páginas con estructura no estándar o de generación dinámica.

## Roles

### Abstract roles
No tienen una representación directa en la interfaz de usuario, pero sirven como roles base o "plantillas" para otros roles más concretos. Estos son:
+ **command:** objeto que puede ser activado por el usuario para realizar una acción.
	+ Roles Concretos Relacionados: button, menuitem, menuitemcheckbox, menuitemradio.
+ **composite:** widget que contiene varios objetos secundarios que, cuando se combinan, forman un único objeto interactivo.
	+ Roles Concretos Relacionados: grid, tree, select, scrollbar.
+ **input:** objeto que permite al usuario ingresar información, como texto o valores numéricos.
	+ Roles Concretos Relacionados: textbox, checkbox, radio, spinbutton.
+ **range:** widget que permite al usuario seleccionar un valor dentro de un rango.
	+ Roles Concretos Relacionados: progressbar, slider, spinbutton.
+ **roletype:** rol abstracto que sirve como base para todos los roles en WAI-ARIA.
	+ Roles Concretos Relacionados: Todos los roles de WAI-ARIA.
+ **section:** sección de contenido que forma parte de una estructura más grande.
	+ Roles Concretos Relacionados: alert, log, status, tabpanel.

### Landmark roles
Son roles específicos que se utilizan para identificar y etiquetar secciones clave de una página web.

|**Rol WAI-ARIA**|**Etiqueta HTML5**|
|---|---|
|banner|header|
|navigation|nav|
|main|main|
|complementary|aside|
|contentinfo|footer|
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Landmark Roles</title>
</head>
<body>

  <header role="banner">
    <h1>Logo y Título Principal</h1>
    <p>Eslogan de la empresa</p>
  </header>

  <nav role="navigation">
    <ul>
      <li><a href="#">Inicio</a></li>
      <li><a href="#">Productos</a></li>
      <li><a href="#">Servicios</a></li>
      <li><a href="#">Contacto</a></li>
    </ul>
  </nav>

  <main role="main">
    <article>
      <h2>Últimas Noticias</h2>
      <p>Contenido de la noticia 1...</p>
      <p>Contenido de la noticia 2...</p>
    </article>

    <section>
      <h2>Destacados</h2>
      <p>Contenido destacado 1...</p>
      <p>Contenido destacado 2...</p>
    </section>
  </main>

  <aside role="complementary">
    <h2>Anuncios</h2>
    <p>Publicidad o información adicional</p>
  </aside>

  <footer role="contentinfo">
    <p>&copy; 2023 Nombre de la Empresa. Todos los derechos reservados.</p>
    <nav>
      <ul>
        <li><a href="#">Política de Privacidad</a></li>
        <li><a href="#">Términos y Condiciones</a></li>
      </ul>
    </nav>
  </footer>

</body>
</html>

```

### Document structure roles
Proporcionan una manera de describir la organización y la estructura de las páginas web, especialmente cuando la estructura no se puede expresar de manera adecuada mediante las etiquetas HTML estándar. Estos son:
+ **application:** región de la página web que funciona como una aplicación independiente y que los cambios en esa región no afectarán el resto de la página.
+ **article:** componente que forma parte de una página o aplicación web que es considerado un artículo independiente, como un artículo de noticias, un blog o un comentario.
+ **cell:** identifica una celda en una tabla.
+ **columnheader:** encabezado de una columna en una tabla.
+ **definition:** contenido que proporciona una definición en un glosario o diccionario.
+ **directory:** identifican una lista de elementos que representan un directorio o una lista de recursos, como un índice de enlaces.
+ **document:** región principal de un documento, proporcionando información sobre el contenido principal de la página.
+ **feed:** región que contiene una secuencia de artículos o eventos, como en una fuente de noticias o en un feed de actividad.
+ **figure:** componente que contiene un elemento autónomo, como una imagen, gráfico o diagrama, junto con su leyenda.
+ **group:** elementos relacionados en una página, proporcionando información sobre la relación entre ellos.
+ **heading:** encabezados en una página, proporcionando información jerárquica sobre la estructura de la página.
+ **img:** imagen, proporcionando información semántica sobre el contenido visual.
+ **list y listitem:** listas y elementos de lista, respectivamente, proporcionando información sobre la relación entre ellos.
+ **math:** contenido que contiene notación matemática o fórmulas.
+ **none:** no tiene un rol semántico.
+ **presentation:** indica que un elemento no debe ser tratado como un componente semántico, desactivando cualquier funcionalidad adicional asociada con un rol.
+ **region:** región de la página que es independiente del contenido circundante y que puede ser considerada y navegada como una unidad.
+ **row, rowgroup y rowheader:** filas, grupos de filas y encabezados de fila en tablas.
+ **separator:** separador visual o semántico entre elementos relacionados.
+ **table:** tabla, proporcionando información sobre su estructura y función.
+ **term:** términos en un glosario o diccionario.
+ **toolbar:** barra de herramientas.

Un ejemplo de uso:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Document Structure Roles</title>
  <style>
    /* Estilos CSS para el ejemplo con HTML + CSS */
    .list {
      margin: 0;
      padding: 0;
      list-style: none;
    }

    .item {
      margin: 5px 0;
    }
  </style>
</head>
<body>

  <h1>Ejemplo de Document Structure Roles</h1>

  <section>
    <h2>HTML Nativo</h2>
    <ul>
      <li>Elemento lista 1</li>
      <li>Elemento lista 2</li>
      <li>Elemento lista 3</li>
    </ul>
  </section>

  <section>
    <h2>HTML + CSS (Sin WAI-ARIA)</h2>
    <div class="list">
      <p class="item">Elemento lista 1</p>
      <p class="item">Elemento lista 2</p>
      <p class="item">Elemento lista 3</p>
    </div>
  </section>

  <section>
    <h2>HTML + CSS (Con WAI-ARIA)</h2>
    <div class="list" role="list">
      <p class="item" role="listitem">Elemento lista 1</p>
      <p class="item" role="listitem">Elemento lista 2</p>
      <p class="item" role="listitem">Elemento lista 3</p>
    </div>
  </section>

</body>
</html>
```

### Widget roles
Se utilizan para describir objetos de la interfaz de usuario con los que los usuarios pueden interactuar. Los widget pueden ser:

+ Widgets Compuestos:
	- **combobox:** cuadro combinado que combina una caja de texto con una lista desplegable.
	- **grid:** cuadrícula.
	- **listbox:** lista de elementos, donde se puede seleccionar uno o más elementos.
	- **menu, menubar:** menús y barras de menú.
	- **tablist:** lista de pestañas, donde se puede seleccionar una pestaña para mostrar su contenido.
	- **tree, treegrid:** estructuras de árbol, útiles para organizar información jerárquica.
+ Widgets Simples:
	- **alert:** mensaje de alerta para el usuario.
	- **button:** botón interactivo.
	- **checkbox:** casilla de verificación.
	- **dialog:** cuadro de diálogo o ventana emergente.
	- **gridcell:** celda en una cuadrícula.
	- **link:** enlace.
	- **progressbar:** barra de progreso.
	- **radio:** botón de opción.
	- **scrollbar:** barra de desplazamiento.
	- **tab, tabpanel:** pestañas y su contenido asociado.
	- **textbox:** caja de texto.
	- **tooltip:** mensaje emergente con información adicional.

Un ejemplo de uso:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Roles de Widget</title>
</head>
<body>

  <form>
    <label for="username">Select a username:</label>
    <input type="text" name="username" onchange="is_available()" />
    <p role="alert" class="feedback"></p>
    <!-- El input y el párrafo actúan como un widget combinado de cuadro de texto y alerta. -->
  </form>

  <img src="button.png" alt="Submit" role="button" id="button" onclick="do_submit();">
  <!-- La imagen se presenta como un botón interactivo. -->

  <script>
    function is_available() {
      // Lógica para comprobar la disponibilidad del nombre de usuario.
      document.querySelector('.feedback').innerText = 'Username is available.';
    }

    function do_submit() {
      // Lógica para enviar el formulario cuando se hace clic en la imagen del botón.
      document.querySelector('form').submit();
    }
  </script>

</body>
</html>
```

## Estados y propiedades

### Atributos de widgets
Los atributos de widgets son propiedades y estados que se utilizan para mejorar la accesibilidad de los elementos interactivos en una página web. Estos atributos proporcionan información adicional sobre la función, comportamiento y estado actual de un widget.

Propiedades de Widgets:
- **aria-autocomplete:** Indica si un campo de entrada de texto admite la función de autocompletar.
- **aria-errormessage:** Asocia un mensaje de error a un elemento cuando hay un error.
- **aria-haspopup:** Indica si un elemento tiene un menú emergente.
- **aria-label:** Proporciona una etiqueta descriptiva para un elemento que no tiene texto visible.
- **aria-level:** Indica el nivel de encabezado para un elemento.
- **aria-modal:** Indica si un elemento forma parte de un cuadro de diálogo modal.
- **aria-multiline:** Indica si un campo de texto admite múltiples líneas de entrada.
- **aria-multiselectable:** Indica si un grupo de elementos puede tener múltiples elementos seleccionados al mismo tiempo.
- **aria-orientation:** Indica la orientación espacial de un elemento.
- **aria-placeholder:** Proporciona un texto de marcador de posición para un campo de entrada de texto.
- **aria-readonly:** Indica si un campo de entrada de texto es de solo lectura.
- **aria-required:** Indica si un campo de entrada de texto es obligatorio.
- **aria-sort:** Indica el criterio de ordenación aplicado a un conjunto de elementos.
- **aria-valuemax:** Indica el valor máximo permitido para un elemento con un rango de valores.
- **aria-valuemin:** Indica el valor mínimo permitido para un elemento con un rango de valores.
- **aria-valuenow:** Indica el valor actual de un elemento con un rango de valores.
- **aria-valuetext:** Proporciona un texto descriptivo del valor actual de un elemento con un rango de valores.

Estados de Widgets:
- **aria-checked:** Indica si un elemento de interruptor (como un checkbox o radio) está marcado o desmarcado.
- **aria-disabled:** Indica si un elemento está deshabilitado.
- **aria-expanded:** Indica si un elemento de expansión, como un menú desplegable, está expandido o contraído.
- **aria-hidden:** Indica si un elemento es visible o no para los usuarios.
- **aria-invalid:** Indica si un elemento tiene un valor inválido.
- **aria-pressed:** Indica si un elemento de interruptor (como un botón de alternar) está presionado o no.
- **aria-selected:** Indica si un elemento de lista o opción está seleccionado.

Ejemplo de uso:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Atributos de Widgets</title>
</head>
<body>

  <form>
    <label for="loginName">Identificador de usuario</label>
    <input name="loginName" type="text" aria-required="true" required />
    <!-- El input requiere información y se indica con aria-required -->

    <label for="passwd">Contraseña</label>
    <input name="passwd" type="password" aria-required="true" required />
    <!-- El input de contraseña también requiere información -->

    <button name="search">Entrar</button>
    <!-- El botón no tiene atributos ARIA en este ejemplo -->
  </form>

  <a aria-haspopup="true">
    <span class="icon-menu"></span>
  </a>
  <!-- El enlace tiene un menú emergente, indicado con aria-haspopup -->

  <ul aria-expanded="false">
    <!-- La lista no está expandida inicialmente -->
    <li><a>A FIC</a></li>
    <li><a>Estudios</a></li>
    <!-- Elementos de la lista -->
  </ul>

</body>
</html>
```

### Atributos de relación
Los atributos de relación son atributos que describen asociaciones entre elementos que no pueden ser directamente deducidas solo por la estructura del documento. Estos son:
- **aria-activedescendant:** Define el elemento que actualmente tiene el foco de atención dentro de un contenedor, como un menú o una lista.
- **aria-colcount:** Indica el número total de columnas en una tabla o grid.
- **aria-colindex:** Indica la posición de una celda dentro de una columna en una tabla o grid.
- **aria-colspan:** Indica el número de columnas que ocupa una celda en una tabla o grid.
- **aria-controls:** Asocia un control con el elemento que lo afecta o lo controla.
- **aria-describedby:** Asocia un elemento con una descripción más detallada o información adicional.
- **aria-details:** Asocia un elemento con información adicional o detalles que se pueden mostrar o ocultar.
- **aria-errormessage:** Asocia un mensaje de error a un elemento cuando hay un error.
- **aria-flowto:** Indica que el contenido de un elemento puede moverse hacia otro elemento cuando la secuencia de lectura se ajusta.
- **aria-labelledby:** Asocia un elemento con una etiqueta o conjunto de etiquetas que describen su propósito o contenido.
- **aria-owns:** Indica que un elemento es propiedad de otro elemento, como un diálogo propiedad de un botón.
- **aria-posinset:** Indica la posición ordinal de un elemento dentro de un conjunto de elementos relacionados.
- **aria-rowcount:** Indica el número total de filas en una tabla o grid.
- **aria-rowindex:** Indica la posición de una celda dentro de una fila en una tabla o grid.
- **aria-rowspan:** Indica el número de filas que ocupa una celda en una tabla o grid.
- **aria-setsize:** Indica el tamaño total de un conjunto de elementos relacionados.

Ejemplo de uso:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Atributos de Relación en WAI-ARIA</title>
</head>
<body>

  <table aria-colcount="3" aria-rowcount="2">
    <!-- Una tabla con 3 columnas y 2 filas -->

    <tr>
      <!-- Primera fila -->
      <td aria-colindex="1">Celda 1</td>
      <td aria-colindex="2">Celda 2</td>
      <td aria-colindex="3">Celda 3</td>
    </tr>

    <tr>
      <!-- Segunda fila -->
      <td aria-colindex="1" aria-rowindex="2">Celda 4</td>
      <td aria-colindex="2" aria-rowindex="2">Celda 5</td>
      <td aria-colindex="3" aria-rowindex="2">Celda 6</td>
    </tr>
  </table>

  <div id="description" aria-describedby="additional-info">
    <!-- Un elemento con una descripción asociada -->
    Elemento con Descripción Adicional
  </div>

  <div id="detailed-info" aria-details="additional-info">
    <!-- Un elemento con información adicional asociada -->
    Información Detallada
  </div>

  <div id="error-element" aria-errormessage="error-message">
    <!-- Un elemento con un mensaje de error asociado -->
    Elemento con Mensaje de Error
  </div>
  <div id="error-message" role="alert" aria-live="assertive" style="display:none;">
    <!-- El mensaje de error asociado -->
    ¡Error! Este es un mensaje de error importante.
  </div>

</body>
</html>
```

### Live regions
Los Live Regions son utilizados para indicar que el contenido de una región puede cambiar de forma dinámica sin que el usuario interactúe directamente con ella. Notifica cambios o actualizaciones importantes en tiempo real. 

Algunos de los roles son:
- **alert:** Indica que la región contiene información importante que requiere atención inmediata del usuario.
- **log:** Utilizado para regiones que reciben mensajes o eventos del sistema, como registros de actividades.
- **marquee:** Se usa para regiones de contenido que se desplazan automáticamente, similar a un texto en movimiento.
- **status:** Indica que la región contiene información sobre el estado o progreso de una tarea.
- **timer:** Se utiliza para regiones que representan un temporizador o cuenta regresiva.

Algunos de los atributos que se usan son:
- **aria-atomic:** Indica si los cambios en el contenido de la región deben ser considerados como un todo o solo parte por parte. Si es "true", se considera como un todo; si es "false" (predeterminado), se considera parte por parte.
- **aria-live off | polite | assertive:** Este atributo define cómo se debe tratar el contenido dinámico. "off" significa que no se anunciarán cambios, "polite" significa que los cambios se anunciarán cuando no haya actividad del usuario, y "assertive" significa que los cambios se anunciarán inmediatamente, incluso si hay actividad del usuario.
- **aria-relevant additions | additions text | removals | text | all:** Indica qué tipos de cambios deben ser anunciados. "additions" para agregar nuevo contenido, "additions text" para agregar nuevo contenido textual, "removals" para eliminar contenido, "text" para cambios en el contenido textual existente, y "all" para todos los tipos de cambios.

El estado principal es:
+ **aria-busy:** Indica que la región está actualmente en un estado de actividad o procesamiento. Se utiliza para indicar al usuario que se está realizando una tarea en segundo plano.

Un ejemplo de uso:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo de Live Regions</title>
</head>
<body>

  <div id="live-region" role="status" aria-live="assertive" aria-relevant="all">
    <!-- Live Region -->
    Contenido dinámico: <span id="dynamic-content">Inicial</span>
  </div>

  <script>
    // Función para actualizar el contenido dinámico en el Live Region
    function actualizarContenidoDinamico() {
      var liveRegion = document.getElementById('live-region');
      var dynamicContent = document.getElementById('dynamic-content');

      // Simular un cambio dinámico
      dynamicContent.textContent = '¡Actualización dinámica realizada!';

      // Avisar a los usuarios a través de ARIA Live Region
      liveRegion.setAttribute('aria-busy', 'true');
      setTimeout(function () {
        liveRegion.setAttribute('aria-busy', 'false');
      }, 2000); // Después de 2 segundos, indicar que la tarea ha finalizado
    }

    // Llamar a la función después de un breve intervalo
    setTimeout(actualizarContenidoDinamico, 3000); // Después de 3 segundos, actualizar el contenido
  </script>

</body>
</html>
```