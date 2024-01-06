[[Interfaces Persoa Máquina]]

## Flexibilidad
Lo que se suele hacer en las páginas web para adaptar bien el tamaño se conoce como Responsive web design. Se basa en adaptar el layout, adaptarse al dispositivo mediante los media queries y hacer las imágenes flexibles.

Se deben utilizar tamaños relativos. Para obtenerlos se calculan como:

$\frac{\text{target}}{\text{context}} = \text{result}$

Donde target es el tamaño del elemento y context el tamaño del contenedor.

### Tipografías flexibles
Se utilizan unidades relativas para escalar el tamaño fuente (em y rem). "em" es relativo al tamaño de fuente del elemento padre más cercano, mientras que "rem" es relativo al tamaño de fuente del elemento raíz html.

```
body {
	font -size: 100 %;
}

h1 { 
	font -size: 1.5em;
} 

p { 
	font -size: 0.875em;
}
```

Otra forma es con las viewport units. "vw" y "vh" equivalen al 1% del ancho y alto del viewport. Por ejemplo: 
```
h2 {
	font -size : 6vw; 
}

h4 { 
	font -size : 3vw; 
}
```

La combinación de los dos trucos permite al navegador calcular el tamaño dinámicamente:
```
html {
	font-size: calc(1em+1vw);
}
```

### Grid flexible, margin y padding
El grid de una página html también se calcula con la fórmula anterior. Una equivalencia entre unidades absolutas y relativas sería:
+ Unidades absolutas:
```
main { 
	margin: 0 auto; 
	width: 900px; 
}

section { 
	width: 600px; 
	float: left; 
}

aside {
	width: 300px;
	float: right;
}

section p {
	margin: 30px; 
} 

section div {
	width: 300px; 
	padding: 12px; 
} 
```

+ Unidades relativas:
```
main {
	width: 100 %;
}

section { 
	width: 66.6666 %;
	float: left;
}

aside { 
	width: 33.3333 %;
	float: right; 
}

section p {
	margin: 5 %; 
}


section div { 
	width: 50 %; 
	padding: 4 %;
}
```

### Flexbox
Es un modelo de diseño en CSS que permite el diseño de diseño de cajas de un contenedor de manera más eficiente y predecible cuando se trabaja con diseños en una dimensión (ya sea en una fila o en una columna). La idea central de Flexbox es proporcionar un sistema de diseño más eficiente y predecible en comparación con los modelos tradicionales basados en bloques y en línea.

#### Ejemplo 1
```
.container { 
	display: flex; 
	flex -direction: row;
	flex -wrap: nowrap;
}

.item { 
	background -color: lightsalmon; 
	border: solid 1px black;
}
```
![[flexbox1.png]]

#### Ejemplo 2
```
.container { 
	display: flex; 
	flex -direction: row; 
	flex -wrap: wrap; 
} 

.item { 
	background -color: lightsalmon; 
	border: solid 1px black; 
	width: 200px; 
}
```

![[flexbox2.png]]

#### Ejemplo 3
```
.container {
	display: flex;
	flex -direction: row; 
	flex -wrap: wrap;
	gap: 10px; 
} 

.item {
	background -color: lightsalmon; 
	border: solid 1px black; 
	flex: 1 100px; 
} 

.item:nth-of-type(2) { 
	flex: 2 200px; 
}
```

![[flexbox3.png]]

#### Ejemplo 4
```
.container {
	display: grid; 
	grid -template -columns: 1fr 2fr 1fr 1fr 1fr;
	grid -gap: 10px;
} 

.item { 
	background -color: lightsalmon;
	border: solid 1px black; 
}
```

![[flexbox4.png]]

#### Ejemplo 5
```
.container {
	display: grid; 
	grid -template -columns: 1fr 2fr;
	grid -gap: 10px; 
}
```
![[flexbox5.png]]

#### Ejemplo 6
```
.container {
	display: grid; 
	grid -template -columns: repeat(auto -fill , minmax(200px, 1fr));
	grid -gap: 10px; 
}
```

![[flexbox6.png]]

### CSS media queries
Las media queries en CSS son utilizadas para aplicar estilos específicos basados en características del dispositivo, como la anchura de la pantalla, la altura, la orientación, el tipo de dispositivo, entre otros.

+ Condicionales
```
/* Estilos por defecto para pantallas pequeñas */
body {
  font-size: 16px;
}

/* Media Query para pantallas más grandes */
@media screen and (min-width: 600px) {
  body {
    font-size: 18px;
  }
}

/* Otra Media Query para pantallas aún más grandes */
@media screen and (min-width: 900px) {
  body {
    font-size: 20px;
  }
}

```

+ Device pixel ratio
```
/* Estilos por defecto para todos los dispositivos */
div {
  border: 1px solid black;
}

/* Media Query basada en Device Pixel Ratio */
@media only screen and (min--moz-device-pixel-ratio: 2),
       only screen and (-o-min-device-pixel-ratio: 2/1),
       only screen and (-webkit-min-device-pixel-ratio: 2),
       only screen and (min-device-pixel-ratio: 2) {
  div {
    border: 2px solid red; /* Estilos específicos para dispositivos de alta densidad de píxeles (retina) */
  }
}
```

### Imágenes flexibles
Debemos escalar las imágenes a medida que escalamos el grid. No había una solución estándar hasta HTML 5.1. Podemos usar imágenes SVG.

Para hacer una imagen flexible al tamaño del contenedor:
```
img {
	max-width: 100 %; 
}
```

Selección en base a la densidad de píxeles:
```
<img src = "im-300w.jpg"
	srcset="img_300w.jpg 1x, img_600w.jpg 2x"
	width="300"
	height="300"
	alt="Description"
/>
```

Selección en base a viewport (w es el tamaño de imagen y vw el tamaño relativo de viewport):
```
<img src = "im-300w.jpg"
	srcset="img_300w.jpg 300w, img_600w.jpg 600w"
	sizes="(max-width: 640 px) 100 vw, (max-width: 960 px) 75 vw, 300px"
	alt="Description"
/>
```

Selección por breakpoint:
```
<picture>
	<source media="(min-width=960px)" srcset="im-large.jpg">
	<source media="(min-width=575px)" srcset="im-medium.jpg">
	<img src="im-small.jpg" alt="Desc"/>
</picture>
```

## Marco de trabajo
Existen 2 opciones para trabajar con el CSS adaptativo:
+ Adaptar el diseño para escritorio y hacer las modificaciones correspondientes.
+ Empezar primero por el diseño para móvil.

Se puede hacer con hojas CSS diferentes o mediante media queries. 

### Patrones responsive
1. **Tiny Tweaks (Pequeños ajustes):**
    - **Descripción:** Este patrón implica realizar pequeños ajustes en los estilos y la disposición de los elementos para adaptarse a pantallas más pequeñas.
    - **Ejemplo:** Cambiar el tamaño de la fuente, ajustar los márgenes y espaciados para que se vean y funcionen mejor en pantallas más pequeñas.
2. **Column Drop (Caída de columnas):**
    - **Descripción:** En este patrón, las columnas se reorganizan y se apilan verticalmente en dispositivos más pequeños para adaptarse al espacio disponible.
    - **Ejemplo:** En una disposición de dos columnas en una pantalla grande, las columnas se convierten en una única columna en una pantalla más pequeña.
3. **Mostly Fluid (Mayormente fluido):**
    - **Descripción:** Este patrón utiliza porcentajes para el ancho de los elementos, lo que permite cierta flexibilidad. Sin embargo, puede haber puntos de quiebre específicos para ajustar el diseño en diferentes tamaños de pantalla.
    - **Ejemplo:** Un diseño de tres columnas donde el ancho de cada columna está definido en porcentajes, lo que permite cierta adaptabilidad, pero aún puede tener puntos de quiebre para reorganizar el diseño.
4. **Layout Shifter (Cambiador de diseño):**
    - **Descripción:** En este patrón, se realizan cambios significativos en el diseño en diferentes puntos de quiebre, reorganizando completamente la disposición de los elementos.
    - **Ejemplo:** Un diseño con varias configuraciones, como una sola columna para dispositivos pequeños, dos columnas para medianos y tres columnas para grandes.
5. **Off Canvas (Fuera de lienzo):**
    - **Descripción:** Este patrón implica ocultar parte del contenido fuera del área visible en dispositivos más pequeños y revelarlo mediante interacción del usuario, como un menú deslizable desde el lateral.
    - **Ejemplo:** Un menú de navegación que se encuentra fuera del área visible en pantallas pequeñas y se muestra cuando el usuario hace clic en un icono de menú.

![[responsive1.png]]

![[responsive2.png]]