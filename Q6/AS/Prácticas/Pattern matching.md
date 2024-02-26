[[Elixir]]

Ejercicios asociados:
+ [[Kitchen calculator]]
+ [[Protein translation]]
+ [[Triangle]]
+ [[Perfect numbers]]
+ [[Meetup]]
+ [[Tournament]]
+ [[Alphametics]]
+ [[Queen attack]]
+ [[Wordy]]
+ [[Bowling]]
+ [[Poker]]

# 1.Definición
El pattern matching consiste en comparar un valor con un patrón específico y descomponer o extraer información de ese valor basándose en su estructura.

```elixir
case {1, 2} do
  {0, _} -> "First element is 0"
  {_, 0} -> "Second element is 0"
  {_, _} -> "Both elements are not 0"
end

# Output: "Both elements are not 0"
```

Generalmente se usa el operador `=`. Funciona cuando la parte izquierda del igual tiene el mismo patrón que la derecha. Asigna los valores de las variables de la derecha a las de la izquierda.

```elixir
{a, b} = {1, 2}
```

Se puede usar `_` para ignorar valores.

```elixir
{:ok, number, _} = {:ok, 5, [4.5, 6.3]}
```

## 1.1.Funciones
Se puede hacer pattern matching con las cabeceras de las funciones. Solo se invocará a las funciones cuyos argumentos coincidan con los de la cabecera.

```elixir
defmodule Example do
	def named_function(:a = atom_variable) do
		{atom_variable, 1} 
	end 
end

Example.named_function(:a)  # {:a, 1}
```

# 2.Operador pin
El operador pin `^` sirve para evitar que se redefina una variable y fuerza a que haga match con su valor original.
```elixir
number = 10 
{:ok, ^number, _} = {:ok, 5, [4.5, 6.3]}

# => ** (MatchError) no match of right hand side value: {:ok, 5, [4.5, 6.3]}
```