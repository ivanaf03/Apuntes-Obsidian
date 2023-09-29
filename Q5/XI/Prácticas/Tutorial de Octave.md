[[Xestión de Infraestruturas]]

### Aspectos básicos
+ Para que no se muestre un el resultado de un comando en la terminal se finaliza con un ';'.
+ Los comentarios se escriben con '%'.
+ El manual de un comando se consigue con 'help (comando)'.
+ Se recomienda iniciar los programas con 'clear; close all;'.

### Vectores
##### Creación de un vector
```
z=1:40; %Crea un vector con los números del 1 al 40
z=1:2:20; %Crea un vector de números separados 2 unidades
z=20:-2:1; %El paso también puede ser negativo
```

##### Extracción de valores
```
%Las posiciones empiezan en 1, no en 0
z(20); %Devuelve el valor de la posición 20
z(1:4); %Devuelve los valores de las posiciones 1, 2, 3 y 4
z(1:2:5) %Devuelve los valores de las posiciones 1, 3 y 5
```

##### Asignación de valores
```
z(20)=10; %Asigna el valor 10 en la posición 20
z(1:4)=[1 2 3 4] %Asigna estos 4 valores en las posiciones del 1 al 4
```

##### Operaciones con vectores
```
v1+v2; v1-v2; %Suma o resta
v1*.v2; %Producto elemento a elemento
(v1)'*v2; v1*(v2)'; %Producto matricial
v1./v2; %División elemento a elemento
v1.^v2; %Potencias elemento a elemento
```

### Matrices
##### Matriz de ceros
```
Z=zeros(5,5); %Matriz de todo ceros
```

##### Extracción de valores
```
Z(1,1); %Devuelve el valor de la posición 1,1
Z(1:3,1); %Devuelve los valores de las posiciones 1, 2 y 3 de la primera columna
```

##### Asignación de valores
```
Z(1,1)=4; %Asigna el valor 4 en la posición 1,1
Z(1:5,1)=1:5; %Asisgna los valores del 1 al 5 en las posiciones de la 1 a la 5 en la primera columna
```

+ Las operaciones son iguales que las de los vectores

### Operadores lógicos, relacionales y bucles
Los operadores lógicos son '&', '|' y '~'. Se usan, por ejemplo, para crear vectores de 0s y 1s. Por ejemplo:
```
v1=randi([1, 3], 1, 5);
v2=randi([1, 3], 1, 5);
%Creamos 2 vectores con numeros aleatorios del 1 al 3
%v1 =

   1   1   3   1   1
%v2 =

   1   3   1   1   1
   
(v1>2)|(v2>2)
%Operación lógica
ans =

  0  1  1  0  0
```

##### Operadores relacionales
+ <
+ \>
+ <=
+ \>=
+ ==
+ ~=

##### Bucle for
```
x=0;
for i=1:1:6
	x=x+1;
end;
%x = 5
```

### Gráficas
Para mantener abierto un gráfico y sobrescribirlo se utilizan 'hold on' y 'hold off'.

Otros comandos son:
+ **title:** añade un título
+ **axis:** permite dar valores y limites a los ejes
+ **grid:** añade una cuadrícula
+ **ylabel, xlabel:** etiqueta los ejes

Para crear una figura se usa el comando 'figure'. Podemos añadir varios gráficos en la misma figura con 'subplot'. Por ejemplo:
```
subplot(4,4,1); %Divide la figura en 4 y deja abierto el gráfico 1
```

Podemos dibujar los gráficos con líneas discontinuas o continuas:
```
plot(1:10, ones(1,10)); %Dibuja una línea horizontal continua en y=1 de x=1 a x=10
stem(1:10,ones(10)); %Dibuja puntuos en y=1 de x=1 a x=10
```