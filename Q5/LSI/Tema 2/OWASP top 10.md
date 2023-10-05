[[Tema 2-Information gathering]]

### OWASP
Open Web Application Security Project es una comunidad mundial dedicada a mejorar la seguridad de las aplicaciones web. Fue fundada en 2001 y es conocida por sus recursos, guías y herramientas relacionadas con la seguridad de aplicaciones web. El objetivo principal de OWASP es proporcionar información y recursos prácticos para ayudar a las organizaciones a desarrollar y mantener aplicaciones web seguras. Una de sus líneas de trabajo es el OWASP TOP 10. Cada 4 años emiten este informe, que refleja el estado en todo Internet sobre las vulnerabilidades de las aplicaciones web.

##### Broken access control
Hasta el 2017 siempre eran los problemas de injection los top 1. Actualmente los broken access control son los más problemáticos. Consisten en robos de cuentas, accesos a otros usuarios, etc en aplicaciones mal implementadas. Por ejemplo:
+ IDs inseguros
+ Path traversal
+ Permisos mal colocados

##### Cryptographic failures
Son errores o debilidades en la implementación o el uso de técnicas criptográficas que comprometen la seguridad de un sistema o una comunicación cifrada.

##### Injections
Son problemas que afectan a las bases de datos o sistema de servidores. Al meter ciertos parámetros a malas validaciones, se puede acceder a ficheros del sistema, datos de usuarios, accesos restringidos, etc. Por ejemplo.
+ SQL
+ OS
+ LDAP
+ XSS (Cross-site scripting)

##### Insecure design
+ XXE (XML External Entities)

##### Security misconfiguration

##### Vulnerable and outdated components

##### Autentication

##### Soff and data integrity

##### Monitorize and log

##### Server side request forgery

### ZAP y WAF
Es una herramienta que permite rastrear las vulnerabilidades OWASP en una aplicación web. Otra herramienta de auditoría de análisis de vulnerabilidades es blindelephant. 

Existe otra herramienta llamada waf w00f que realiza un fingerprinting a una url que comprueba si por medio de la conexión existe algún WAF. Si no hay ningún WAF, es muy sencillo atacar.