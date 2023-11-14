[[Tema 4-Gestión de la configuración software]]

### ¿Qué es la GCS o SCM?
``` mermaid
graph TD;
  integridad --> desarrollo;
  integridad --> gestión;
  integridad --> control;
  control --> gestión-de-configuracion-software;
  gestión-de-configuracion-software --> integridad;

```

GCS (Gestión de Configuración Software) o SCM (Software Configuration Manager) es el arte de identificar, organizar, control y coordinar las modificaciones del desarrollo software. Su objetivo es maximizar la productividad minimizando los errores. 

Cubre todas las actividades para identificar y definir los ECS (Elementos de Configuración Software). Una relación, por ejemplo, sería:
```
.c ----> .o ----> .out
```

Controla los cambios y modificaciones en el ciclo de vida del software, es decir, con mantenimiento incluido, conociendo todos los estados del software y verificando la completitud y consistencia de ellos. 