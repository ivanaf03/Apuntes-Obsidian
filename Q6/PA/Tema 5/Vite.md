[[Tema 5-Desarrolllo basado en componentes React]]

# 1.Qué es Vite?
Para facilitar el desarrollo de frontend en JS se puede usar la herramienta Vite. Proporciona plantillas para diversos frameworks JS, por ejemplo, para aplicaciones SPA con React.

Se crea una aplicación con:

```
npm create vite@latest my-app -- --template react
```

Si un fichero utiliza expresiones JSX tiene que ser un `.jsx`, no un `.js`.

## 1.1.Estructura de ficheros
El `index.html` contiene dentro del `<body>` un div con el id "root".

```html
<div id="root"></div>
```

El fichero `src/main.jsx` contiene lo necesario para renderizar el componente App, que se renderiza con el div con el id "root".

```javascript
import App from './App';
...
const root=ReactDOM.createRoot(document.getElementById('root'));
root.render(
	<React.StrictMode>
		<App/>
	</React.StrictMode>
)
```

## 1.2.Modo desarrollo
Podemos arrancar un servidor de desarrollo.

```
cd my-app
npm run dev
http://localhost:5173
```

Esto devuelve el contenido de `index.html`, que incluye una referencia a `/src/main.jsx`. El resto de ficheros se van sirviendo al navegador según sea necesario. El código que modificamos se actualiza automáticamente en el navegador. 

Vite transforma los JSX a JavaScript para que se puedan ejecutar en el navegador.

## 1.3.Modo producción
Podemos pasar el código a una versión apta para producción.

```
cd my-app
npm run build
```

Al pasar el código a modo producción:
+ [>] Los JSX pasan a JavaScript.
+ [>] Los JS más modernos pasan a JS antiguo para que funcionen en navegadores antiguos.
+ [>] Minimiza el código JS en un solo fichero.
+ [>] Minimiza el código CSS.
+ [>] `index.html` contiene referencias a estos dos ficheros.
