[[Interfaces Persoa Máquina]]

### WCAG
Está enfocado en los contenidos de las páginas web. El estándar acual es el WCAG 2.2, pero ya se trabaja en el 3. Se divide en niveles:
+ A: Esencial
+ AA: Soporte ideal (recomendado)
+ AAA: Casos especializados

Los contenidos deben ser:
+ **Perceptibles:** consiste en proporcionar alternativas de texto para vídeos, imágenes, etc; proporcionar alternativas a medios dependientes del tiempo como vídeos o audios, presentar contenidos en diferentes formas y facilitar la visualización de estos.
+ **Operable:** consiste en crear webs accesibles sin ratón, proporcionar tiempo suficiente para leer, diseñar contenidos que eviten por ejemplo epilepsia, proporcionar ayudas como volver atrás, o facilitar entradas a través de métodos que no sean teclado, como gestos.
+ **Entendible:** consiste en hacer contenidos legibles y entendibles, hacer que la apariencia sea predecible, es decir, similares a páginas que ya existen y ayudar a los usuarios a corregir errores.
+ **Robusta:** maximizar la compatibilidad con los navegadores.

### Sección 508
##### Requisitos
+ **Técnicos:** codificación de la página web compatible con tecnologías asistidas.
+ **Funcionales:** sistema usable por personas con discapacidad.
+ **Soporte:** documentación con soporte e información alternativa.

##### En imágenes y tablas
+ HTML con title/alt y caption:
```
<img src="logo.png" alt="Logo empresa" />
<table>
<caption>Titulo de la tabla</caption>
...
</table>
```

+ WAI-ARIA para descripciones más largas y para marcar imágenes decorativas.

##### Contenidos repetitivos
Utilizar métodos para saltar bloques de contenido que se repitan en varias páginas:
```

```

Debe tener el mismo orden todo lo que se repita.

##### Colores
La información no puede depender del color. Hay que usar colores que contrasten bien el fondo y el primer plano. No debemos:
+ Usar colores para marcar acciones.
+ Indicar errores marcando bordes en rojo.
+ No marcar campos obligatorios en un formulario de un solo color.

##### Formularios
Agrupar elementos relacionados en un formulario:

##### Enlaces y botones
Proporcionar una descripción clara del objetivo de cada enlace o botón. Para ello:
+ Evitar enlaces y botones de pulsa aquí y ver más.
+ No usar el mismo texto para varios enlaces o botones.
+ El destino de cada enlace o botón se debe indicar.

##### Teclado y focus
Todas las funcionalidades deben ser operables mediante un teclado.

##### Hoja de estilos
No incluir imágenes de fondo como imágenes de fondo. No incluir los selectores before y after porque el lector de pantalla no lo leerá. Evitar posicionamientos absolutos para que los elementos esté siempre en el mismo lugar.

##### Títulos y cabeceras
Toda página web debe tener un título descriptivo.

Utilizar cabeceras descriptivas. Utilizar h1, h2... sin saltar niveles. Modificar el tamaño con CSS.

##### Elementos multimedia
Audios con transcripción textual
Vídeos sin sonido con transcripción textual o pista de sonido
Vídeo con subtítulos

##### Otros
Evutar scroll
CAPTCHAS no solo de imagenes
Incluir el idioma general de la página

##### Pruebas
+ Toolbars
+ Navagador sin CSS y JS
+ Navegador solo texto
+ Navegar sin ratón
+ Tecnologías asistivas como lectores de pantalla

### WAI-ARIA
Es necesario sólo si el HTML no tiene la semántica adecuada.