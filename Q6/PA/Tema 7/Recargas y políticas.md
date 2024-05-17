[[Tema 7-Frontend de una tienda de comercio electrónico]]
$\space$
## 1.Recargas
Las recargas ocurren cuando se modifica el código del frontend mientras se está en modo desarrollo. Puede ocurrir:
+ Se recarga solo un componente al editar un archivo JSX.
+ Se recarga todo el frontend al editar un fichero JavaScript. Todas las variables pierden su valor.
$\space$
### 1.1.Recarga total
Cuando se recarga todo, si no se controla, los datos del usuario desaparecerán y el desarrollador tendría que volver a autenticarse. En PA Shop, si el usuario está autenticado, `App` envía un POST a `/users/loginFromServiceToken` para reautenticar al usuario automáticamente a partir del token. 

El estado local de los componentes se pierde.

Para poder hacer esto, el token JWT se guarda en el almacenamiento Web del navegador. Los navegadores para ello proporcionan la API `Storage`, que permite guardar pares clave-valor.
$\space$
#### 1.1.1.Storage
El navegador proporciona dos tipos:
+ **localStorage:** los datos no tienen fecha de expiración.
+ **sessionStorage:** los datos están vinculados a la página web. Si se cierre desaparecen. Lo usa PA Shop.
$\space$
## 2.Política Same-origin y CORS
El código frontend se descarga de un lugar distinto al código backend.

![[cors.png]]
$\space$
### 2.1.Same-origin
Los navegadores implementan la política Same-origin. El origen de una URL es la combinación de protocolo, host y puerto. Esta política obliga a que un script descargado de un origen no puede interactuar con scripts de otro origen.
$\space$
### 2.2.CORS
Para poder utilizar aplicaciones web SPA es necesario es mecanismo CORS (Cross-Origin Resource Sharing). Las respuestas del backend contienen cabeceras con los permisos que tendrán los scripts del navegador para poder interactuar con el backend.