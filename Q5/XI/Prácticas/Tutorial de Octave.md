[[Xestión de Infraestruturas]]

### Aspectos básicos
+ Para que no se muestre un el resultado de un comando en la terminal se finaliza con un ';'.
+ Los comentarios se escriben con '%'.
+ El manual de un comando se consigue con 'help (comando)'.
+ Se recomienda iniciar los programas con 'clear; close all;'.

### Vectores
Para crear un vector:
```
z=1:40; %Crea un vector con los números del 1 al 40
z=1:2:20; %Crea un vector de números separados 2 unidades
z=20:-2:1; %El paso también puede ser negativo
```

Para extraer sus valores:
```
%Las posiciones empiezan en 1, no en 0
z(20); %Devuelve el valor de la posición 20
z(1:4); %Devuelve los valores de las posiciones 1, 2, 3 y 4
z(1:2:5) %Devuelve los valores de las posiciones 1, 3 y 5
```

Para asignar valores:
```
z(20)=10; %Asigna el valor 10 en la posición 20
z(1:4)=[1 2 3 4] %Asigna estos 4 valores en las posiciones del 1 al 4
```

Operaciones:
```
v1+v2; v1-v2; %Suma o resta
v1*.v2; %Producto elemento a elemento
(v1)'*v2; v1*(v2)'; %Producto matricial
v1./v2; %División elemento a elemento
v1.^v2; %Potencias elemento a elemento
```

### Matrices
Matriz de ceros:
```
Z=zeros(5,5); %Matriz de todo ceros
```

Para extraer sus valores:
```
Z(1,1); %Devuelve el valor de la posición 1,1
Z(1:3,1); %Devuelve los valores de las posiciones 1, 2 y 3 de la primera columna
```

Para asignar valores:
