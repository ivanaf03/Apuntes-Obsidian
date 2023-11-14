[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Capa modelo
Es aquella que implementa todos los casos de uso de la aplicación de forma independiente de la interfaz gráfica. Se divide en dos subcapas:
+ **Capa de acceso a datos:** accesos a bases de datos y a otras aplicaciones
+ **Capa lógica de negocio:** implementa los casos de uso de la capa modelo usando la capa de acceso a datos para leer y escribir en la base de datos

### Capa interfaz
Se divide en dos:
+ **Capa interfaz gráfica:** interfaz gráfica que permite a los usuarios utilizar las funcionalidades de la capa modelo
+ **Capa servicios:** interfaz orientada a que otras aplicaciones utilicen las funcionalidades de la capa modelo a través de la capa "acceso a servicios"

### Ejemplo: aplicación web bancaria
##### Capa modelo
La capa modelo en la encargada de implementar los casos de uso como crear las cuentas, eliminarlas, realizar transferencias, etc. Se implementan en la capa lógica de negocio , que llama a la capa de acceso a datos para usar la base de datos. Por ejemplo, una transferencia:

```
leerSaldoOrigen()  # Llamada a acceso a datos
if saldoOrigen>importe{
	saldoOrigen=saldoOrigen-importe
	esribirSaldoOrigen  # Llamada a acceso a datos
	saldoDestino=saldoDestino+importe
	escribirSaldoDestino  # Llamada a acceso a datos
} else{
	throw("saldo insuficiente")
}
```

##### Capa interfaz
La capa interfaz se encarga de comunicar la aplicación con otras fuentes. La capa interfaz gráfica es la parte que se encarga de interactuar con los usuarios. La capa servicios ofrece una API para que otras aplicaciones puedan interactuar con ella.

### Ventajas de la separación
+ Cada capa puede ser desarrollada por un perfil diferente de personal
+ Es posible reutilizar la capa modelo en interfaces diferentes y por varias aplicaciones
+ Los cambios en unas capas no afectan a otras
+ Cada capa suele poder ejecutarse en máquinas diferentes
+ Es posible replicar la capa modelo sin afectar a las aplicaciones consumidoras
