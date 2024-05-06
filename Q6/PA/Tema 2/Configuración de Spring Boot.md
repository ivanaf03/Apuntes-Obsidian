[[Tema 2-Capa acceso a datos con Spring y JPA]]
$\space$
## 1.Configuración de Spring Boot
La configuración de Spring Boot está en `src/main/resouces/application.{properties,yml}`. Puede estar en formato properties o en formato YAML. Para la capa de acceso a datos permite configurar:
+ El pool de conexiones.
+ Configuraciones de Hibernate.
$\space$
### 1.1.Formato properties
```properties
spring.datasource.url=@dataSource.url@ 
spring.datasource.username=@dataSource.user@ 
spring.datasource.password=@dataSource.password@ 
# maven sustituye estos 3 valores por los especificados en el archivo en cuestión

spring.datasource.dbcp2.max-total=4 
spring.datasource.dbcp2.max-idle=2 
spring.datasource.dbcp2.max-wait-millis=10000 
spring.datasource.dbcp2.remove-abandoned-on-borrow=true
spring.datasource.dbcp2.remove-abandoned-timeout=60 
spring.datasource.dbcp2.log-abandoned=true 
spring.datasource.dbcp2.validation-query=SELECT 1 
spring.jpa.hibernate.ddl-auto=none 
spring.jpa.hibernate.naming.physical-strategy=...
...
```
$\space$
### 1.2.Formato YAML
```yaml
spring:
  datasource:
    url: "@dataSource.url@"
    username: "@dataSource.user@"
    password: "@dataSource.password@"
    dbcp2:
      max-total: 4
      max-idle: 2
      max-wait-millis: 10000
      remove-abandoned-on-borrow: true
      remove-abandoned-timeout: 60
      log-abandoned: true
      validation-query: "SELECT 1"
  jpa:
    hibernate:
      ddl-auto: none
    naming:
      physical-strategy: "..."
...

# Tienen que ser indentados con espacios blancos, no sirven tabulados
```