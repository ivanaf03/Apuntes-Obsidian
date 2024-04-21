[[Tema 2-La máquina y el mundo]]

## 1.Cómo se elabora la especificación?
Para demostrar que los requisitos son satisfacibles por el software se hace una especificación de requisitos. Funciona como puente entre el entorno y el sistema, actuando como interfaz.

### 1.1.Formalización
Si un software que satisface la especificación se instala en un entorno, entonces el sistema podrá cumplir con los requisitos propuestos,

$$S, E\rightarrow R$$

 La formalización no es infalible. Por ejemplo, en un sistema de gestión de tráfico a veces los coches no paran aunque el semáforo esté en rojo.

### 1.2.Designación
Una designación es una conversión entre los términos del cliente expresando los requisitos y los términos de la especificación. Esta debe estar en un lenguaje formal, cercana a la implementación del sistema.

## 2.El entorno en la especificación
Muchas veces debemos tener en cuenta el entorno en la especificación de requisitos. 

Por ejemplo, tenemos como requisito que si un paciente tiene una desviación en el pulso, el sistema emitirá un sonido. La especificación simplemente indica que el sistema emite un sonido.

Sin embargo, esto estaría incompleto. Debemos tener en cuenta que debe haber alguien escuchando en el entorno.