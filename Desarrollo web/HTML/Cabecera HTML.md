[[Desarrollo web]]

# 1.Función de la cabecera
La cabecera `<head>` es el elemento que se encarga de contener los metadatos del documento, como el título, las referencias a CSS, a favicon, a JS, etc. Su contenido no aparece en la página web.

# 2.Elementos de la cabecera
## 2.1.Título
El título de una página web es el nombre que aparece en la pestaña del navegador. Además también es lo que aparece al añadir una página a marcadores y para las búsquedas. 

```html
<title>Título del documento</title>
```

## 2.2.Metadatos
Generalmente se utiliza la etiqueta `<meta>`. Algunos ejemplos de metadatos son la codificación de caracteres del documento. También se pueden indicar cosas como el autor de la página o una descripción. Esto es útil para los motores de búsqueda.

```html
<meta charset="utf-8" />
<!-- universal -->

<meta charset="ISO-8859-1" />
<!-- caracteres latinos -->
```

```html
<meta name="author" content="Iván Álvarez Fernández"/>
<meta name="descripction" content="Esta es mi primera página web"/>
```

# 3.Agregar un favicon
Los favicon son pequeños iconos que se muetran al lado del título en las pestañas del navegador.

Para crear un favicon podemos crea una imagen de 16x16 y guardarla como `.ico`. Luego lo añadimos al `head`.

```html
<link rel="shortcut icon" href="favicon/favicon.ico" type="image/x-icon"/>
```

# 4.Uso de CSS y JS
Podemos vincular al documento HTML archivos CSS y JS para añadir estilos y funcionalidades.

```html
<link rel="stylesheet" href="styles.css" />
<!-- css -->

<script src="functions.js"></script>
<!-- javascript -->
```

