[[Interfaces Persoa Máquina]]

## CORS (Cross-Origin HTTP Request)
Es una política de seguridad implementada en los navegadores web para restringir las solicitudes de recursos, como archivos de estilo, imágenes o scripts, que se realizan desde un dominio (origen) hacia otro dominio diferente al de la página actual.

Cuando una página web alojada en el dominio A intenta realizar solicitudes HTTP a recursos en el dominio B, se considera una solicitud "cross-origin". Por razones de seguridad, los navegadores aplican la política de CORS para determinar si permiten o bloquean estas solicitudes.

## ¿Qué es Ajax?
Es una combinación de objetos o funciones del navegador para realizar peticiones de datos con JS y HTML DOM para mostrar esos datos. Permite actualizar páginas web de formas asíncronas sin recargar la página completa. 

CORS entra en juego cuando estas solicitudes AJAX se realizan a un dominio diferente al de la página web actual. Antes de CORS, las solicitudes AJAX entre dominios estaban restringidas por la política de mismo origen (Same-Origin Policy), que impedía que el código JavaScript en una página web realizara solicitudes a un dominio diferente al de la propia página. CORS fue introducido para flexibilizar esta restricción, permitiendo a los servidores especificar qué dominios pueden realizar solicitudes.

### Fetch
La Fetch API es una interfaz en JavaScript que proporciona una forma más flexible y poderosa de realizar solicitudes HTTP asincrónicas (AJAX) en comparación con las antiguas técnicas basadas en XMLHttpRequest. La función fetch devuelve una Promise, un proxy que permite asociar código para gestionar el resultado de la petición asincrónica, que se resuelve en un objeto Response, que contiene información sobre la respuesta HTTP.

La sintaxis básica es:
```
fetch(resource [, init ])

/*
resource: El recurso que se solicita, puede ser una URL o un objeto `Request`.

init: Configuración opcional de la petición, que incluye propiedades como `method`, `headers`, `body`, `mode`, `credentials`, `cache`, `redirect`, etc.
*/
```

Un ejemplo básico de uso sería:
```
fetch('https://api.example.com/data')
  .then(response => {
    // Manejar la respuesta
    if (!response.ok) {
      throw new Error('Error de red: ' + response.status);
    }
    return response.json();
  })
  .then(data => {
    // Hacer algo con los datos
    console.log(data);
  })
  .catch(error => {
    // Manejar errores
    console.error('Error:', error);
  });
```

1. Petición GET con respuesta JSON:
```
fetch("https://dog.ceo/api/breeds/image/random")
  .then(response => {
    if (response.ok) {
      // Devuelve una Promise a un objeto JSON
      return response.json();
    } else {
      throw Error('Error');
    }
  })
  .then(response => {
    // Modifica el DOM con los datos de la respuesta
    document.querySelector("#image1").src = response['message'];
  })
  .catch(error => {
    // Captura solo errores de red (por ejemplo, cuando el servidor está abajo)
    console.error(error.message);
  });
```

2. Petición POST enviando datos en FormData:
```
var formData = new FormData();
formData.append('username', username);
formData.append('password', password);

fetch('http://localhost:5000/login', {
  method: 'POST',
  body: formData
})
.then(response => {
  if (response.status == 401) {
    throw Error('Bad username or password');
  }
  return response.json();
})
.then(response => {
  token = response['access_token'];
  do_login();
})
.catch(error => document.querySelector('p#error-formpost').innerHTML = error.message);
```

3. Petición POST enviando datos en JSON:
```
var data = {
  'username': username,
  'password': password
};

fetch('http://localhost:5000/login', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data)
})
.then(response => {
  if (response.status == 401) {
    throw Error('Bad username or password');
  }
  return response.json();
})
.then(response => {
  token = response['access_token'];
  do_login();
})
.catch(error => document.querySelector('p#error-jsonpost').innerHTML = error.message);
```

4. Petición GET con autenticación vía token:
```
var headers = new Headers();
headers.append('Authorization', 'Bearer ' + token);

fetch('http://localhost:5000/protected', {
  headers: headers
})
.then(response => response.json())
.then(response => {
  document.querySelector('p#response-ex2').innerHTML = 'Logged in as ' + response['logged_in_as'];
})
.catch(error => console.error(error.message));
```

5. Petición GET con respuesta Blob:
```
var headers = new Headers();
// Comenta estos encabezados para habilitar el almacenamiento en caché
headers.append('pragma', 'no-cache');
headers.append('cache-control', 'no-cache');

fetch('http://localhost:5000/image', {
  headers: headers,
})
.then(response => response.blob())
.then(response => {
  // Crea una URL para la imagen Blob y la muestra en el DOM
  var urlCreator = window.URL || window.webkitURL;
  var imageUrl = urlCreator.createObjectURL(response);
  document.querySelector("#image2").src = imageUrl;
})
.catch(error => console.error(error.message));
```