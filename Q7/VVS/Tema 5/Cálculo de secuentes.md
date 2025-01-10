[[Tema 5-Cáculo de secuentes]]

## Qué es el cálculo de secuentes?
> [!abstract] Definición de cálculo de secuentes
> El cálculo de secuentes es un sistema formal con el que se puede derivar la validez de una fórmula mediante la manipulación de fórmulas puramente simbólicas.

Se utilizan reglas para demostrar la verdad de las declaraciones tanto en lógica proposicional como en lógica de primer orden. Esto permite ser implementado en sistemas que demuestren teorías de forma automática.

Se basa en considerar un objetivo inicial en el problema e ir descomponiéndolo en subobjetivos cada vez más simples para llegar a situaciones que hagan que el problema sea trivial.

![[secuentes.png]]

## Qué es un secuente?
> [!abstract] Definición de secuente
> Un secuente es un par de la forma $\Gamma \vdash \Delta$, donde las dos partes son conjunto finitos de fórmulas.

La parte izquierda se llama antecedente y la derecha consecuente. El secuente se lee como que $\Delta$ se deduce de $\Gamma$.

### Fórmula asociada a un secuente
Si todas las fórmulas del antecedente son ciertas, alguna del secuente también lo es. Por tanto, otra forma de expresar un secuente sería:
$$ A_1 \land A_2 \land ... \land A_n \rightarrow  B_1 \lor B_2 \lor ... \lor B_n$$

El secuente es válido si esa fórmula es válida.

## Reglas de secuentes
Se realizan pruebas para atrás, es decir, se parte de una conjetura y se descompone en subobjetivos mediante reglas de inferencia. Se reducen los subobjetivos hasta llegan a un axioma.

### Regla de corte
![[regla_corte.png]]

### Regla del axioma
> [!abstract] Definición de axioma
> Un axioma es un secuente en el que aparece la misma fórmula en el antecedente que en el consecuente.

Un axioma se considera cierto y no genera ningún subobjetivo.

### Reglas estructurales
![[reglas_estructurales.png]]

### Reglas de cálculo
![[reglas_calculo.png]]

## Proceso de cálculo de secuentes
Para demostrar la validez de una fórmula mediante cálculo de secuentes se parte de que la fórmula es el secuente objetivo inicial. Se aplican reglas para generar subobjetivos y se van reduciendo mediante la regla del axioma. Si se alcanza un subobjetivo al que no se le puede aplicar ninguna regla, la fórmula no es válida.

### Cálculo de predicados
En el cálculo de predicados es necesario agregar más reglas. 

![[calculo_predicados.png]]

Se utiliza la constante de Skolem, $c$, que es una nueva constante que no aparece en el secuente. Una vez se instancia, se puede reutilizar. 