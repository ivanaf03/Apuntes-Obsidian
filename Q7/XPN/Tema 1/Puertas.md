[[Tema 1-Modelado de procesos con BPMN]]

## Qué son las puertas?
Las puertas o gateways son los elementos que permiten controlar el flujo del proceso. No pueden representar trabajo, son solamente una herramienta que sirve para controlar el flujo del proceso.

![[error_comun_bpmn.png]]

### Puerta XOR
La puerta XOR puede funcionar como split o como merge. Cuando tiene una sola entrada y varias salidas, se produce un split y el fujo solo puede continuar por una de las dos salidas, la que cumpla la condición. Las condiciones de las salidas son excluyentes. Hay que tener cuidado, ya que los motores de automatización no comprueban que las condiciones sean excluyentes. 

De forma similar, cuando funciona como merge, unifica las entradas en un solo flujo de salida.

![[xor_bpmn_merge_split.png]]

No es recomendable que la puerta tenga más de una entrada y más de una salida a la vez. También se puede indicar una salida por defecto sin que obligatoriamente tenga asociada una condición.

Se pueden modelar bucles con dos puertas XOR.

![[loop_bpmn.png]]

### Puerta AND
La puerta AND permite ejecutar abrir y ejecutar varios caminos en paralelo. 

![[and_bpmn.png]]

### Puerta OR
Funciona de forma similar a la puerta XOR, pero permite activar más de una de sus salidas de forma simultánea.

![[or_bpmn.png]]
