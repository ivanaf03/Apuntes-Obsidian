[[Tema 9-Web Forms]]

## Qué es el view state?
> [!abstract] Definición de view state
> El view state es un mecanismo de ASP.NET que mantiene el estado de los controles entre diferentes llamadas al servidor.

### Funcionamiento
Antes de renderizar la página a HTML y enviarla al cliente, ASP.NET examina las propiedades de los controles de la página. Si alguno ha cambiado de valor, se anota en una colección nombre-valor. Se guarda en base64 en el form como un campo oculto.

La próxima vez que se haga un postback, se carga la página en base a los valores iniciales, se actualizan los controles con los valores del view state, se actualiza la página con los valores enviados desde el cliente y se gestionan los eventos.

Esto permite liberar los recursos del servidor después de cada petición y hacerlo muy escalable. El problema es que aumenta el tamaño de las páginas.