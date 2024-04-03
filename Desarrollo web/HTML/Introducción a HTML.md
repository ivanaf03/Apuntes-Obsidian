[[Desarrollo web]]

# 1.Qué es HTML?
HTML es un lenguaje de marcas que indica al navegador cómo estructurar las páginas web que visita. Se compone de elementos, que sirven para encerrar partes del contenido que actúan de distinta manera.

# 2.Elementos
Los elementos de HTML se componen de:
+ *Etiqueta de apertura:* nombre del elemento escrito entre `< >`.
+ *Contenido:* contenido del elemento.
+ *Etiqueta de cierre:* nombre del elemento escrito entre `< >`. Se pone una barra diagonal delante del elemento.

## 2.1.Elementos anidados
Se pueden meter elementos dentro de otros elementos. Algunos muy típicos son los que permiten diferentes estilos de texto.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <b>Texto en negrita</b><br>
    <strong>Otro texto en negrita</strong><br>

    <i>Texto en cursiva</i><br>
    <em>Otro texto en cursiva</em><br>

    <b><i>Texto en negrita y cursiva</i></b><br>
    <strong><em>Otro texto en negrita y cursiva</em></strong><br>

    <u>Texto subrayado</u><br>

    <s>Texto tachado</s><br>
    <strike>Otro texto tachado</strike><br>

    Texto<sup>superíndice</sup><br>

    Texto<sub>subíndice</sub><br>
</body>
</html>
```

## 2.2.Elementos vacíos
Algunos elementos no tienen etiqueta de cierre. Algunos solo tienen una etiqueta de apertura, que suelen servir para insertar algo en el documento. Por ejemplo, las imágenes `<img>` o el salto de línea `<br>`.

## 2.3.Atributos
Los atributos son parte de los elementos que contienen información adicional sobre el elemento. Se escriben como `atributo="valor"`. Un elemento puede tener más de un atributo.

```html
<p class="parráfo">Hola mundo!</p>
```

### 2.3.1.Ejemplo: atributos de imagen
El elemento `<img>` incluye los atributos:
+ *`src`:* ubicación de la imagen.
+ *`alt`:* descripción de la imagen.
+ *`width`:* ancho de la imagen.
+ *`heigth`:* alto de la imagen.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Imagen con atributos</title>
</head>
<body>
    <h2>Imagen con atributos</h2>
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTFF74lS-zQmpG46UlrZp9U2qKfmn2CMTg77uruQt7-4g&s" alt="Gato adorable" width="400" height="300">
</body>
</html>
```

### 2.3.2.Atributos booleanos
Algunos atributos no tienen valores. Se llaman atributos booleanos. Solo pueden tener un valor, que generalmente es el mismo que le nombre del propio atributo.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atributo booleano en HTML</title>
</head>
<body>
    <h2>Ejemplo de atributo booleano en HTML</h2>
    <input type="checkbox" checked disabled> Opción seleccionada y deshabilitada<br>
    <input type="checkbox" checked> Opción seleccionada<br>
    <input type="checkbox" disabled> Opción deshabilitada<br>
</body>
</html>
```

# 3.Estructura básica
Un documento HTML generalmente suele tener esta estructura. Podemos obtenerla escribiendo en VSCode `html:5`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
</body>
</html>
```

+ *`<!DOCTYPE html>`:* versión de HTML del documento.
+ *`<html lang="en">`:* elemento raíz del documento que engloba toda la página. Contiene el atributo `lang` que indica el idioma, en este caso inglés.
+ *`<head>`:* contenedor de metadatos y recursos externos.
+ *`<meta charset="UTF-8">`:* codificación de caracteres del documento.
+ *` <meta name="viewport" content="width=device-width, initial-scale=1.0">`:* propiedades de la ventana. Inicializa el ancho de la ventana al ancho del dispositivo y el zoom al 100%.
+ *`<title>`:* título del documento que aparece en las pestañas del navegador.
+ *`<body>`:* contenedor principal del documento.

# 4.Caracteres especiales
Ciertos caracteres están reservados en HTML. Pueden escribirse con el operador `&`.

| Carácter literal | Referencia de carácter equivalente |
|------------------|------------------------------------|
| <                | `&lt;`                             |
| >                | `&gt;`                             |
| "                | `&quot;`                           |
| '                | `&apos;`                           |
| &                | `&amp;`                            |

# 5.Comentarios
Los comentarios en HTML se escriben con `<!-- comentario -->`. Son ignorados por los navegadores. Al igual que en todos los lenguajes sirven para documentar el código.