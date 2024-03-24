[[Tema 4-Capa de servicios REST con Spring]]

# 1.Introducción
Usamos la librería spring-web para implementar la capa de servicios REST. Al usar Spring Boot, el servicio debe tener una clase anotada con `@SpringBootApplication` con un método `main`.

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

## 1.1.Ejecución del backend
Al ejecutar `mvn spring-boot:run` busca la clase con esta notación e invoca al main. El main arranca un servidor de aplicaciones, el contenedor de objetos escanea los `.class`, crea los beans correspondientes y deja el backend listo para recibir peticiones.

Al ejecutar `mvn package` se genera un fichero `.jar`. Tenemos dos opciones:
+ [>] *Ejecutar `java -jar target/pa-shop-backend.jar`:* es un fat JAR formado por:
	+ [>] Todos los `.class` del backend.
	+ [>] Todos los `.jar` de las dependencias.
	+ [>] Un fichero con metadatos para el nombre completo de la clase con la anotación `@SpringBootApplication` . La máquina virtual de Java ejecuta el `main` de esa clase.
+ [>] *Instalar `target/pa-shop-backend.war` en un servidor de aplicaciones de Java estándar:* se pasa el `.jar` a `.war` y, una vez instalado, el contenedor de objetos de Spring estará listo para recibir peticiones.