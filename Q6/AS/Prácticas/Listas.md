[[Elixir]]

Ejercicios asociados:
+ [[Language list]]
+ [[Strain]]
+ [[Sublist]]
+ [[Flatten array]]
+ [[Spiral matrix]]
+ [[Scale generator]]
+ [[Sieve]]
+ [[List ops]]

# 1.Definición
Las listas son un tipo básico en Elixir. Son inmutables, no pueden ser modificadas. Una operación que actúa sobre una lista devuelve una nueva lista. Permiten el uso de funciones del módulo `Enum` y del módulo `List`.

```elixir
doble = Enum.map([1, 2, 3, 4, 5], &(&1 * 2))

IO.inspect doble  # [2, 4, 6, 8, 10]
```

## 1.1.Notación
Se denotan entre corchetes. Pueden estar vacías o contener ítems de cualquier tipo.

```elixir
lista_vacia = []

lista_con_elementos = [1, 2, 3, 4, "Hola", []]
```

### 1.1.1.Notación Head-tail 
Elixir implementa las listas como listas enlazadas. Cada nodo está formado por un elemento y la lista restante. Se separan con el operador `|`.

```elixir
# [1]
[1 | []]

# [1, 2, 3]
[1 | [2 | [3 | []]]]
[1 | [2, 3]]
```

Puede haber más de un valor a la izquierda de `|`.

```elixir
[1, 2 | [3]]  # [1, 2, 3]
```

Se puede usar esta notación  para añadir elementos a una lista.

```elixir
list = [1, 2]

[3 | list]  # [1, 2, 3]
```

# 2.Operaciones
Muchas de las operaciones que se pueden hacer en una lista vienen en el módulo `List`.

## 2.1.Añadir un elemento al final
Hay dos formas de hacerlo. Una es usando el operador `++`. Es una operación muy lenta.

```elixir
[1, 2, 3] ++ [4] ++ [5] ++ [6]
```

La otra forma, mucho más eficiente, es añadirlo al principio e invertir la lista.

```elixir
lista = [6 | [5 | [4 | [3, 2, 1]]]]
inverted = Enum.reverse(lista)
```

## 2.2.Funciones del Kernel
El módulo Kernel también trae algunas funciones muy útiles para las listas.

```elixir
lista = [1, 2, 3, 4, 5]

hd(lista)  # 1

tl(lista)  # [2, 3, 4, 5]

length(lista)  # 5

10 in lista  # false
```