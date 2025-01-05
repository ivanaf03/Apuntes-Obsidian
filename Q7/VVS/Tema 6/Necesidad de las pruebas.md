[[Tema 6-Validación automática]]

## Qué es un bug?
> [!abstract] Definición de bug
> Un bug es una situación donde el software hace algo que no debería, ya sea por un error o por no cumplir con la especificación.

Se considera bug tanto no cumplir con lo que dice la especificación como no cumplir con ciertos requisitos no funcionales, que pese a no estar especificados, se tienen que sobreentender. Por ejemplo, que el software vaya muy lento, que sea muy complicado de usar, etc.

### Cuándo ocurren?
Los bugs se pueden dar en:
+ **Especificación:** puede deberse a que la especificación ha cambiado, no está bien documentada, etc.
+ **Diseño:** puede ocurrir que se cambie el diseño y no se documente, que haya aspectos sin el detalle suficiente, etc.
+ **Código:** puede darse por un código muy complejo, efectos no esperados, falta de tiempo, etc.

### Coste de los bugs
Se estima que el coste de los bugs puede suponer la mitad del coste del proyecto. El problema es que el coste no es fijo, crece dependiendo de en que etapa se encuentren los bugs.

Se estima que cuesta 10 céntimos cambiar una especificación, entre 1 y 10 euros corregir un error en desarrollo o haciendo las pruebas y sobre 100 euros si lo encuentra el cliente. No hacer suficientes pruebas puede salir muy caro. Además, el mantenimiento de un software suficientemente probado es mucho menos caro.

## Utilidad de las pruebas
Una prueba exitosa es aquella que encuentra errores. Sin embargo, no pueden demostrar que el software no tiene fallos ni que cumple a la perfección la especificación. 

La verdadera utilidad es mostrar los errores que existen. También pueden mostrar que los intentos de hacer fallar el software con respeto a la especificación fallan, lo que permite identificar especificaciones no completas o ambiguas. Lo único que muestran es si no se han encontrado disconformidades con la especificación.

### Problemas
Generalmente, no es posible probar un software complejo completamente. Además, no siempre se pueden arreglar todos los errores que se encuentran.

Otro problema es la paradoja del pesticida, cuántas más pruebas se hacen, menos errores se encuentran. Pero cuántos más errores se encuentran, más errores tiene el sistema.

Hacer pruebas no evita los errores, pero sí garantiza una mayor confianza en el software.

### Objetivos
Las pruebas tienen dos objetivos principales:
+ **Defect testing:** revelar bugs o encontrar inconsistencias lo antes posible.
+ **Validation testing:** ganar la máxima confianza posible en que el software cumple con la especificación.
