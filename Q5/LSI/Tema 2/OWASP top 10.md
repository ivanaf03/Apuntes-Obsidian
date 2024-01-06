[[Tema 2-Information gathering]]

## OWASP
Open Web Application Security Project es una comunidad mundial dedicada a mejorar la seguridad de las aplicaciones web. Fue fundada en 2001 y es conocida por sus recursos, guías y herramientas relacionadas con la seguridad de aplicaciones web. El objetivo principal de OWASP es proporcionar información y recursos prácticos para ayudar a las organizaciones a desarrollar y mantener aplicaciones web seguras. Una de sus líneas de trabajo es el OWASP TOP 10. Cada 4 años emiten este informe, que refleja el estado en todo Internet sobre las vulnerabilidades de las aplicaciones web.

### 1-Broken access control
Hasta el 2017 siempre eran los problemas de injection los top 1. Actualmente los broken access control son los más problemáticos. Consisten en robos de cuentas, accesos a otros usuarios, etc en aplicaciones mal implementadas. Por ejemplo:
+ IDs inseguros
+ Path traversal
+ Permisos mal colocados

### 2-Cryptographic failures
Errores o debilidades en la implementación o el uso de técnicas criptográficas que comprometen la seguridad de un sistema o una comunicación cifrada.

### 3-Injections
Problemas que afectan a las bases de datos o sistema de servidores. Al meter ciertos parámetros a malas validaciones, se puede acceder a ficheros del sistema, datos de usuarios, accesos restringidos, etc. Por ejemplo.
+ SQL
+ OS
+ LDAP
+ XSS (Cross-site scripting)

### 4-Insecure design
Problemas relacionados con el diseño inseguro de sistemas, incluyendo vulnerabilidades como XXE (XML External Entities), que permiten a los atacantes acceder y manipular datos sensibles a través de la interpretación maliciosa de archivos XML externos.

### 5-Security misconfiguration
Errores en la configuración de seguridad que pueden resultar en vulnerabilidades. Esto incluye configuraciones inseguras de servidores, permisos incorrectos y ajustes inadecuados.

### 6-Vulnerable and outdated components
Riesgos asociados con el uso de componentes desactualizados o vulnerables en el sistema, como bibliotecas, frameworks o software de terceros.

### 7-Autentication
Problemas relacionados con la autenticación, como contraseñas débiles, falta de multifactorial, y vulnerabilidades en el proceso de autenticación.

### 8-Soff and data integrity
Compromisos en la integridad de software y datos, incluyendo ataques que manipulan o alteran información crítica.

### 9-Monitorize and log
La falta de una monitorización adecuada y registros detallados que puedan alertar sobre actividades sospechosas o ataques en curso.

### 10-Server side request forgery
Vulnerabilidades que permiten a un atacante realizar solicitudes a través del servidor, potencialmente accediendo a recursos internos o servicios no autorizados.

## ZAP y WAF
OWASP ZAP es una herramienta que permite rastrear las vulnerabilidades OWASP en una aplicación web. Otra herramienta de auditoría de análisis de vulnerabilidades es blindelephant. 

Existe otra herramienta llamada WAFWOOF que realiza un fingerprinting a una url que comprueba si por medio de la conexión existe algún WAF. Si no hay ningún WAF, es muy sencillo atacar.