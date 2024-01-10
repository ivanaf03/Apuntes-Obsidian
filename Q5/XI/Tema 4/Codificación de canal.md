[[Tema 4-Fundamentos de la codificación de canal]]

## Transmisión de información
Una fuente transmite información (voz, audio, vídeo…) a través de un canal ruidoso (línea telefónica, enlace óptico, inalámbrico, medio de almacenamiento…). El objetivo es recuperar esa información con el menor número de bits erróneos posible.

La codificación de canal consiste en añadir redundancia para combatir los posibles errores. Añadimos redundancia transmitiendo N bits por cada K bits. La tasa de codificación es:
$$R=K/N$$
![[codificación.png]]
El canal alterará algunos de los bits transmitidos de modo que el vector (palabra) de bits recibidos c' puede ser diferente al transmitido c.

## Canal simétrico binario
El Canal Simétrico Binario (Binary Symmetric Channel, BSC) con parámetro p. Este canal tiene la propiedad de alterar el bit transmitido con una probabilidad p. Es "simétrico" porque la probabilidad de error es la misma para ambos bits posibles (0 y 1).

Envía varias veces la información redundada. El bit que aparezca más veces redundado es el que se elige. La decodificación falla cuando el número de errores es mayor que el número de bits correctos.

## Código binario
Un código binario es una colección de elementos, donde cada elemento es una palabra código. Cada palabra código está formada por bits binarios (0 y 1). La longitud del código, denotada como m, es el número de bits en cada palabra código. La cardinalidad del código, denotada como N, es el número total de palabras código en el conjunto y se calcula como N=2^k. 

### Ejemplo: Código de 3-Repetición
Para un código de 3-repetición, las palabras código son {000, 111}.
- **Longitud del Código (m):** En este caso, m=3 ya que cada bit se repite tres veces.
- **Cardinalidad del Código (N):** Dado que hay dos palabras código posibles (000 y 111), la cardinalidad es N=2.
- **Tasa de Codificación (R):** En este caso, R=1/3​, ya que cada bit de la palabra fuente se representa con tres bits en la palabra código.

### Distancia y errores
La distancia es la medida de la diferencia entre dos palabras código.

La distancia de Hamming mide la diferencia entre dos palabras código de igual longitud contando la cantidad de posiciones en las cuales los bits difieren. Por ejemplo, la distancia de Hamming entre "1101" y "1001" es 1, ya que difieren en un solo bit.

El peso de Hamming de una palabra código es simplemente la cantidad de bits que tienen un valor diferente de cero. Es equivalente a la distancia de Hamming entre la palabra código y un vector de ceros de la misma longitud. En otras palabras, es la cantidad de "unos" en la palabra código.

La distancia mínima de un código es la distancia mínima entre cualesquiera dos palabras código.

Para decodificar dada una palabra recibida, escogemos como palabra transmitida aquella palabra código más próxima en distancia de Hamming.

Los errores que un código puede detectar son:
$$t_{\text{detect}} = d_{\text{min}} - 1$$

Los errores que un código puede corregir son:
$$t_{\text{corrección}} = \lfloor \frac{d_{\text{min}} - 1}{2} \rfloor$$


## Código lineal
Un código binario se denomina "lineal" si es cerrado respecto a la suma de n-tuplas utilizando la operación XOR (o suma módulo 2). Esto significa que la suma de cualquier par de palabras código en el conjunto también pertenece al conjunto.

Todo código binario lineal incluye la palabra cero (la palabra código que consiste en todos los bits igual a cero).

La distancia mínima de un código lineal es igual al peso mínimo de las palabras no nulas.

El peso mínimo de un código es la menor cantidad de bits diferentes entre cualquier par de palabras código diferentes.

La matriz generadora es una matriz que se utiliza para generar los códigos en un código lineal. Cualquier palabra de código puede ser generada multiplicando un vector de información (la palabra original sin errores) por la matriz G.

Supongamos que $G$ es una matriz generadora de un código lineal, y su representación es $G = \left[ \begin{array}{c|c} I & P \end{array} \right]$. Entonces, si $\mathbf{v}$ es un vector de información, la palabra de código $\mathbf{c}$ se obtiene como $\mathbf{c} = \mathbf{v} \cdot G$.

![[hamming 47.png]]
![[hamming 2.png]]
El código dual C⊥ consiste en todos los vectores que son ortogonales a todos los vectores en C. 

La matriz de control de paridad H de un código C es una matriz que define las restricciones de paridad en el código. Un vector v es una palabra de código válida si y solo si:
$$\mathbf{v} \cdot \mathbf{H}^T = 0$$

Se obtiene como: 
$$H = \begin{bmatrix}
1 & 1 & 1 & 0 & 1 & 0 & 0 \\
1 & 1 & 0 & 1 & 0 & 1 & 0 \\
1 & 0 & 1 & 1 & 0 & 0 & 1 \\
\end{bmatrix}
$$

H es P transpuesta y a su lado la identidad.

Un síndrome es la palabra código recibida por H transpuesta. Si da 0 es una palabra código.

### Descodificación óptima
Transmitimos 𝑐, canal suma error 𝑒, recibimos c′ = c + e.

Hay 2n−k posibles síndromes, ya que hay n−k bits de información en la palabra y cada uno puede tener un valor de 0 o 1. Hay 2^n posibles patrones de error, ya que cada uno de los 𝑛n bits de la palabra recibida puede tener un error o no tenerlo.

 Para decodificar la palabra recibida:
 + Se calcula su síndrome s′.
- Se busca en el "standard array" el patrón de error de peso mínimo que corresponde al síndrome s′.
- La suma de este patrón de error a la palabra recibida produce la palabra transmitida original, ya que c′+e=(c+e)+e=c.

La tabla estándar se construye enumerando todos los posibles síndromes (vectores resultantes del producto c′HT) y asociándolos con los patrones de error correspondientes:
![[tabla.png]]

La regla de decodificación es óptima ya que la probabilidad de un patrón de error es mayor que la de cualquier otro con mayor peso.

Si permitimos que el código de Hamming sea NO sistemático, el valor en decimal del síndrome nos indica la posición del bit en error.
![[hamming no sistematico.png]]
### Hamming extendido
Código de Hamming con un bit de paridad adicional que cubre todos los bits, con lo que consigue 𝑑mín = 4. Puede detectar si hubo exactamente 1 ó 2 errores. La capacidad de corrección sigue siendo 1 error. Por ejemplo:
![[hamming extendido.png]]