[[TFG]]
## 1.Instalación
Instalo la última versión de NodeJS desde https://nodejs.org/en.

Después creo un proyecto de Expo:

```
npx create-expo-app ./
```

Instalo las dependencias necesarias:

```
npx expo install expo-router react-native-safe-area-context react-native-screens expo-linking expo-constants expo-status-bar
```

Instalo nativewind y creo un archivo de configuracion de Tailwind:

```
npm install nativewind
npx tailwindcss init
```

Pruebo que el proyecto funcione con:

```
npx expo start
```

Una buena forma es presionando `w` para abrirlo en el navegador. Otra forma es instalando Expo Go en Android y escaneando el QR.

Finalmente, reseteo el ejemplo que trae Expo con:

```
npm run reset-project
```
## 2.Configuración
En `package.json` cambio el name por ezcow.

```json
{

  "name": "ezcow",

  "main": "expo-router/entry",

  "version": "1.0.0",
  
  ...
```

En `app.json` cambio el name por EZCow y el slug y el scheme por ezcow.

```json
"expo": {

    "name": "EZCow",

    "slug": "ezcow",

    "version": "1.0.0",

    "orientation": "portrait",

    "icon": "./assets/images/icon.png",

    "scheme": "ezcow",
    
    ...
```

En `babel.config.js` añado el plugin de Tailwind:

```
module.exports = function (api) {

  api.cache(true);

  return {

    presets: ['babel-preset-expo'],

    plugins: ["nativewind/babel"],

  };

};
```

En `tailwind.config.js` añado el directorio components:

```
/** @type {import('tailwindcss').Config} */

module.exports = {

  content: ["./app/**/*.{js,jsx,ts,tsx}", "./components/**/*.{js,jsx,ts,tsx}"],

  theme: {

    extend: {},

  },

  plugins: [],

}
```
## 3.Inicio
En la carpeta `app` creo un fichero `index.tsx`. Gracias a la extensión ES7+ de VSCode puedo crear una plantilla escribiendo "rnfes" y presionando Enter.

