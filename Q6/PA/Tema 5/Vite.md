[[Tema 5-Desarrolllo basado en componentes con React]]

## 1.Qué es Vite?
Vite es una herramienta que facilita el desarrollo de frontend en JavaScript proporcionando plantillas para frameworks de JavaScript, por ejemplo, para aplicaciones SPA con React.

Permite crear una aplicación con:

```
npm create vite@latest my-app -- --template react
```

## 2.Estructura de ficheros Vite
Vite genera automáticamente una estructura de ficheros que crean la base de la aplicación.

### 1.1.Index.html
Es la base de la página web. Contiene el `div` raíz.

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>PA Counter</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

### 1.2.Main.jsx
Renderiza la aplicación React en el elemento HTML con el ID `root`. Además, utiliza `React.StrictMode` para activar el modo estricto de React, que ayuda a identificar y evitar problemas en la aplicación durante el desarrollo.

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

/* Render application. */
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode> // Advertencias sobre fallos en React
    <App/>
  </React.StrictMode>
);
```

## 3.Modos de trabajo
Vite permite trabajar en modo desarrollo, para hacer la aplicación y en modo producción, para generarla.

### 3.1.Modo desarrollo
Se hace con `npm run dev`. Arranca un servidor web local, que abre la página `index.html`. El resto de ficheros JavaScript se van sirviendo al navegador a medida que sea necesario. Vite transforma los ficheros JSX en JavaScript para que se puedan ejecutar en el navegador.

Al modificar el código del frontend se recarga automáticamente en el navegador. 

### 3.2.Modo producción
Se hace con `npm run build`. Genera una carpeta llamada dist que contiene el código transformado en JavaScript minimizado en un solo fichero. También minimiza todo el CSS y lo incluye en el `index.html`. 

El contenido de esta carpeta se puede instalar en un servidor web.




