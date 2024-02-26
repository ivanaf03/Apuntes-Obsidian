[[Elixir]]

Ejercicios asociados:
+ [[Bird count]]
+ [[Satellite]]
+ [[POV]]
+ [[Roman numbers]]
+ [[Strain]]
+ [[Binary search]]
+ [[Binary search tree]]
+ [[Matching brackets]]
+ [[Pascal triangle]]
+ [[Spiral matrix]]
+ [[Sieve]]

# 1.Funciones recursivas
Las funciones recursivas son aquellas que se llaman a sí mismas. Se dividen en:
+ [>] *Caso base:* devuelve un valor sin volver a llamar a la función.
+ [>] *Caso recursivo:* llama a la función modificando los parámetros para no repetir el caso hasta llegar al caso base.

$\space$
Se suelen escribir los casos cada uno en su propia cláusula.

```elixir
def sum([]), do: 0

def sum([h|t]), do: h + sum(t)
```

Puede haber más de un caso base y más de un caso recursivo. 

```elixir
def fibonacci(0), do: 0
def fibonacci(1), do: 1
def fibonacci(n), do: fibonacci(n - 1) + fibonacci(n - 2)
```

## 1.1.Recursión infinita
Si se implementan mal las funciones recursivas pueden dar lugar a recursión infinita. Esto producirá `stack overflow`. Puede ser causado por:
+ [>] Olvidarse de implementar un caso base.
+ [>] No definir el caso base como primera cláusula.
+ [>] No modificar correctamente el argumento en la cláusula recursiva. 

# 2.Bucles
En elixir no existen los bucles. Al ser un lenguaje funcional para realizar bucles se debe hacer de forma recursiva.

```elixir
def loop([]), do: nil

def loop([head | tail]) do
	do_something(head)
	loop(tail)
end
```

Aunque es mucho más práctico para trabajar con listas y enumerados usar el módulo `Enum`.