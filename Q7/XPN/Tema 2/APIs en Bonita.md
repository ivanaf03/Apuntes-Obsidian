[[Tema 2-Automatización de procesos]]

## Acceso al motor desde aplicaciones externas
Normalmente, Bonita se usa para gestionar procesos administrativos, pero se suele implementar la interfaz con otras aplicaciones externas. Para interactuar con Bonita, se utiliza su propia API.

### Ejemplos de peticiones a la API REST de bonita

```java
// Login mediante Bonita Portal

POST http://localhost:8080/bonita/loginservice
Content-Type: application/x-www-form-urlencoded

username=walter.bates&password=bpm&redirect=false

```

```java
// Creación de un proceso en Bonita

POST http://localhost:8080/bonita/API/bpm/case/
Content-Type: application/json
Cookie: JSESSIONID=node01huhak8k3v4t41gwri76z2me9.node0

{
  "processDefinitionId": "1234567890"
}
```

```java
// Lectura del proceso

GET http://localhost:8080/bonita/API/bpm/case/987654321
Cookie: JSESSIONID=node01huhak8k3v4t41gwri76z2me9.node0

```

### APIs de Bonita
Bonita dispone de las siguientes APIs:
+ **application API:** gestión de aplicaciones.
+ **bdm API:** lectura y escritura de objetos del modelo.
+ **bpm API:** acceso a elementos de un proceso.
+ **form API:** mapeo entre formularios y actividades de un proceso.
+ **identity API:** acceso a datos de usuarios.
+ **platform API:** arranque y parada de la plataforma.
+ **portal API:** accesos a páginas.
+ **system API:** acceso a sesión de usuario, internacionalización, etc.
