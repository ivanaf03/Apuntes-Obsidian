[[Tema 2-El lenguaje CSharp]]

## Paso por valor y paso por referencia
Se pasan por valor los datos de tipo:
+ Tipos primitivos.
+ Enumeraciones.
+ Structs.

Se pasan por referencia los datos de tipo:
+ String.
+ Object.
+ Clases.
+ Interfaces.
+ Arrays.

### Boxing y unboxing
Los datos que se pueden pasar por valor se pueden convertir en datos que se pueden pasar por referencia. Esto se llama boxing y unboxing respectivamente.

```CSharp

// boxing
int i = 3;
object obj = i;


// unboxing
int value = (int) obj;
```