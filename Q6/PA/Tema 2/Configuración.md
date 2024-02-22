[[Tema 2-Capa acceso a datos con Spring y JPA]]

# 1. Configuración de Spring Boot
Reside en `src/main/resouces/application.{properties,yml}`. Configura:
+ [>] Pool de conexiones.
+ [>] Hibernate.

Puede estar en formato properties o en formato YAML.

## 1.1. Properties
```properties
spring.datasource.url=@dataSource.url@
spring.datasource.username=@dataSource.user@ 
spring.datasource.password=@dataSource.password@ 
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

## 1.2. YAML
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
```

Tienen que ser identados con espacios blancos, no sirven tabulados.