[[Desarrollo web]]

# 1.Encabezados y párrafos
La mayor parte de los textos están compuestos por encabezados y párrafos. Esto se hace para simplificar la lectura. 

## 1.1.Párrafos
Los párrafos se definen con la etiqueta `<p>`.

```html
<p>Esto es un párrafo</p>
```

## 1.2.Encabezados
Los encabezados sirven principalmente para diferenciar secciones. Se definen con las etiquetas `<h1>` ... `<h6>`.

```html
<h1>Encabezado</h1>
```

### 1.2.1.Jerarquía
Los encabezados deben ir en orden, sin saltarse niveles. Algunos consejos son:
+ [>] Utilizar solo un `<h1>` por página como título principal.
+ [>] No usar más de tres encabezados por página.

# 2.Listas
## 2.1.Listas ordenadas
Se usan para enumerar artículos cuya orden no es importante. Se utiliza la etiqueta `<ul>`. Cada uno de los elementos utiliza la etiqueta `<li>`.

```html
<ul>
  <li>leche</li>
  <li>huevos</li>
  <li>pan</li>
  <li>hummus</li>
</ul>
```

## 2.2.Listas ordenadas
Se usan para enumerar artículos cuya orden importa. Se utiliza la etiqueta `<ol>`. Cada uno de los elementos utiliza la etiqueta `<li>`.

```html
<ol>
  <li>Hervir el agua</li>
  <li>Poner los macarrones</li>
  <li>Esperar 10 minutos</li>
</ol>
```

## 2.3.Listas anidadas
Por supuesto se pueden meter listas dentro de otras listas.

```html
<ol>
    <li>Elemento 1</li>
    <li>Elemento 2
        <ol>
            <li>Subelemento 2.1</li>
            <li>Subelemento 2.2</li>
        </ol>
    </li>
    <li>Elemento 3</li>
</ol>
```

