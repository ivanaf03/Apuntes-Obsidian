[[Tema 2-La máquina y el mundo]]

# ¿Cómo se hace la especificación?
+ [<] **Partes de un requisito:**
+ *R:* parte optativa, expresa lo que el sistema debería cambiar cuando esté funcionando.
+ *E:* parte indicativa, es lo que ya existe, una asunción del entorno.

Para demostrar que los requisitos son satisfacibles por un software hacemos una especificación de este. Todos los artefactos relacionados con nuestro sistema tienen una función en él.

 La formalización no es infalible. Por ejemplo, en un sistema de gestión de tráfico a veces los coches no paran aunque el semáforo esté en rojo.

## Designaciones
Una designación es un `mapping` entre los términos de los requisitos y una especificación formal. Por ejemplo, en la entrada de un parque con un torno giratorio:
+ El cliente dice que quiere una entrada.
+ El sistema reconoce que entrar es girar el torno de la entrada N grados.
+ La especificación es el puente intermedio entre lo que dice el cliente y lo que hace el sistema.

# Ejemplo
Si el requisito es que un paciente tiene una desviación en el pulso, el sistema emite un sonido. La especificación es que emita un sonido. Esto es incompleto, tenemos que tener en cuenta el entorno o dominio. Si no hay nadie escuchando, esto no sería correcto.