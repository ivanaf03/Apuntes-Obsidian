[[Xestión de Proxectos]]

+ Iván Álvarez Fernández
ivan.alvarez.fernandez@udc.es
+ Ivanna Pombo Casais
ivanna.pombo@udc.es
+ Fernando Álvarez Rodríguez de Legísima
fernando.alvarezr@udc.es

## Ejercicio 1
*Tienes 1500 euros disponibles para invertirlos durante los próximos tres años. Al inicio de cada año puedes invertir parte del dinero en depósitos a un año o a dos años. Los depósitos a un año pagan un interés del 4%, mientras que los depósitos a dos años pagan un 7% al final de los dos años. El objetivo es conseguir que al cabo de los tres años tu capital sea lo mayor posible.*
+ Variable de decisión:
$x_{ij}$

$i$ representa el año, $j$ representa la inversión (o 0 si no se invierte). Por ejemplo, $x_{11}$ sería la inversión en el primer año en depósitos a un año.

+ Función objetivo:
$$\text{Maximizar } Z = x_{40}$$
+ Sujeto a:
$$x_{ij} \geq0$$$$x_{10} + x_{11} + x_{12} = 1500$$
$$x_{10} + 1.04x_{11} = x_{20} + x_{21} + x_{22}$$
$$x_{20} + 1.04x_{21} + 1.07x_{22} = x_{30} + x_{31} + x_{32}$$
$$x_{30} + 1.04x_{31} + 1.07x_{32} =\leq= x_{40}$$

## Ejercicio 2
*Se dispone de tres tipos de aviones: A1, A2 y A3 para transportar sacos con alimentos desde un aeropuerto hasta cinco aldeas: V1, V2, V3, V4 y V5, afectadas por inundaciones. La cantidad de alimentos (en unidades adecuadas) que cada avión puede transportar a cada aldea en cada viaje, se da en la siguiente tabla. El número de viajes que puede hacer cada avión se da en la última columna y el número de vuelos que pueden realizarse sobre cada aldea diariamente en la última fila. Encontrar el número de viajes que deberá hacer cada avión a cada aldea de forma que se maximice la cantidad de alimento distribuido por día.*

|    | V1 | V2 | V3 | V4 | V5 | VT |
|----|----|----|----|----|----|----|
| A1 | 10 | 8  | 6  | 9  | 12 | 50 |
| A2 | 5  | 3  | 8  | 4  | 10 | 90 |
| A3 | 7  | 9  | 6  | 10 | 4  | 60 |
| AT | 100| 80 | 70 | 40 | 20 |    |
+ Variable de decisión:
$x_{ij}$

$i$ representa el avión, $j$ representa la aldea. Por ejemplo, $x_{11}$ sería la cantidad de viajes que hace el avión 1 a la aldea 1.

+ Función objetivo:
$$\text{Maximizar } Z = 10x_{11} + 8x_{12} + 6x_{13} + 9x_{14} + 12x_{15}$$$$   + 5x_{21} + 3x_{22} + 8x_{23} + 4x_{24} + 10x_{25}$$ $$  + 7x_{31} + 9x_{32} + 6x_{33} + 10x_{34} + 4x_{35}$$

+ Sujeto a:
$$x_{ij}\geq0$$
$$x_{11} + x_{12} + x_{13} + x_{14} + x_{15} \leq 50$$
$$x_{21} + x_{22} + x_{23} + x_{24} + x_{25} \leq 90$$
$$x_{31} + x_{32} + x_{33} + x_{34} + x_{35} \leq 60$$
$$x_{11} + x_{21} + x_{31} \leq 100$$
$$x_{12} + x_{22} + x_{32} \leq 80$$
$$x_{13} + x_{23} + x_{33} \leq 70$$
$$x_{14} + x_{24} + x_{34} \leq 40$$
$$x_{15} + x_{25} + x_{35} \leq 20$$

+ Resolución (con LPSolve IDE):
```
/* Objective function */
max:  10x11 + 8x12 + 6x13 + 9x14 + 12x15 + 5x21 + 3x22 + 8x23 + 4x24 + 10x25 + 7x31 + 9x32 + 6x33 + 10x34 + 4x35;

/* Variable bounds */

x11 + x12 + x13 + x14 + x15 <= 50;
x21 + x22 + x23 + x24 + x25 <= 90;
x31 + x32 + x33 + x34 + x35 <= 60;
x11 + x21 + x31 <= 100;
x12 + x22 + x32 <= 80;
x13 + x23 + x33 <= 70;
x14 + x24 + x34 <=  40;
x15 + x25 + x35 <= 20;
int x11, x12, x13, x14, x15, x21, x22, x23, x24, x25, x31, x32, x33, x34, x35;
```

+ Resultados obtenidos:
![[XP programación lineal.png]]
Para maximizar la cantidad de alimento se desprecia que haya aldeas que se queden sin alimento:
+ El avión 1 solo viaja a la aldea 1, pero un total de 50 veces, llevando 10 U de alimento de cada vez. Esto nos da 500 U de alimento.
+ El avión 2 hace 90 viajes, 70 a la aldea 3 y 20 a la aldea 5. Esto nos da 560+200=760 U de alimento.
+ El avión hace 60 viajes, 20 a la aldea 2 y 40 a la aldea 4. Esto nos da 180+400=580 U de alimento.

En total, los 3 aviones han llevado 500+580+760=1840 U de alimento.
