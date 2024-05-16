[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Introducción
Usamos la librería spring-web para implementar los servicios REST. Al usar Spring Boot, es necesario que el servicio contenga una clase anotada con `@SpringBootApplication` con un método main para arrancarlo.

```java
package es.udc.pashop.backend;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {

...

    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }

...

}
```
$\space$
### 1.1.Ejecución en modo desarrollo
Al hacer `mvn spring-boot:run` en el directorio del backend la clase anotada invoca al método main. Este método arranca un servidor de aplicaciones. El contenedor de objetos de Spring escanea los ficheros `.class` para encontrar las clases anotadas como bean y crea los beans correspondientes.

Una vez hecho esto el backend queda listo para recibir peticiones.
$\space$
### 1.2.Ejecución en modo producción
Al hacer `mvn package` se genera un fichero `.jar`. Tenemos dos posibilidades:
+ Se ejecuta `java -jar target/pa-shop-backend.jar`. Es un fat jar formado por todos los ficheros `.class` del backend, todos las librerías de las que depende y un fichero de metadatos con el nombre de la clase que corre el main.
+ Generar un .war e instalarlo en un servidor de aplicaciones Java.
