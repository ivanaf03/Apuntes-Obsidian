[[Tema 4-Lógica linear temporal]]

## Sintaxis
La lógica linear temporal parte de un conjunto de átomos o proposiciones, es decir, variables que solo pueden ser cierto o falso. 

$$\Sigma = \{p, q, r\}$$

### Operadores proposicionales
Los operadores son son idénticos a los de la lógica simple:
+ Falso: $\bot$
+ Verdadero: $\top$
+ And: $\land$
+ Or: $\lor$
+ Negación: $\neg$
+ Implicación: $\rightarrow$
+ Doble implicación: $\leftrightarrow$

### Operadores temporales
Para hablar de instancias de tiempo la LLT utiliza operadores modales:
+ **Para siempre:** $\Box$ - p debe ser cierto en todos los instantes.
+ **Eventually:** $\Diamond$ - p va a ser cierto en algún momento del futuro.
+ **En el siguiente instante:** $\bigcirc$ - p es cierto en el siguiente instante.
+ **Hasta que:** $U$ - p es cierto hasta que q sea cierto.
+ **Hasta que (débil):** $W$ - p es cierto hasta que q sea cierto o q nunca ocurre.
+ **Liberación:** $R$ - p debe ser cierto siempre a menos que q ocurra antes.

