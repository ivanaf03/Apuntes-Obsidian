[[Elixir]]

Ejercicios asociados:
+ [[DNA encoding]]
+ [[Prime factors]]
+ [[Dominoes]]
+ [[Simple linked list]]
+ [[List ops]]

# 1.Recursividad de cola
Cuando iteramos sobre listas, strings, etc. necesitamos mucha memoria. Esto no es rápido ni eficiente. 

Para evitar la recursividad no terminal se usan acumuladores. Esto es más que una variable que se pasa en las funciones que guarda el estado actual de la función hasta que llega al caso base, el cual devuelve el acumulador.

Se suelen inicializar en una función privada. Se pone con `do_` por convención.

```elixir
# Count the length of a list without an accumulator 
def count([]), do: 0 
def count([_head | tail]), do: 1 + count(tail) 

# Count the length of a list with an accumulator 
def count(list), do: do_count(list, 0) 
defp do_count([], count), do: count 
defp do_count([_head | tail], count), do: do_count(tail, count + 1)
```