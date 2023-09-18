[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Capa modelo
Es aquella que implementa todos los casos de uso de la aplicación de forma independiente de la interfaz gráfica. Se divide en dos subcapas:
+ Capa de acceso a datos: bases de datos y otras aplicaciones
+ Capa lógica de negocio: implementa los casos de uso de la capa modelo según la interfaz de la capa de acceso a datos
$Lógica\ de\ negocio->Acceso\ a\ datos->Base\ de\ datos$

### Ejemplo: caso de uso transferencia bancaria

Existen 2 usos:
+ Uso humano: capa interfaz gráfica
+ Otra aplicaciones: capa servicios

**Capa modelo:**
```
Leer(saldoOrigen) //Llamada a capa de acceso a datos
si saldoOrigen>importe{
	nuevoSaldoOrigen=saldoOrigen-importe
	//Llamada a capa de acceso a datos
	Escribir(nuevoSaldoOrigen)
	//Llamada a capa de acceso a datos
	Escribir(nuevoSaldoDestino+importe)
} sino {
	lanzarErrorSaldoInsuficiente
}
```

**Capa interfaz gráfica:**
Es una interfaz web que utiliza la capa modelo para permitir a los usuario crear cuentas, buscarlas, hacer transferencias, etc.

**Capa servicios:**
API que puede ser utilizada por otras aplicaciones.
### Ventajas de la separación
+ Cada capa puede ser desarrollada por un perfil diferente de personal
+ Es posible reutilizar la capa modelo en interfaces diferentes y por varias aplicaciones
+ Los cambios en unas capas no afectan a otras
+ Cada capa suele poder ejecutarse en máquinas diferentes
+ Es posible replicar la capa modelo sin afectar a las aplicaciones consumidoras
