[[Elixir]]

Ejercicios asociados:
+ [[Guessing game]]
+ [[Two Fer]]
+ [[Collatz conjecture]]
+ [[Triangle]]
+ [[Leap]]
+ [[Say]]
+ [[Bowling]]

# 1.Condiciones con when
Las guardas se usan complemento del pattern matching. Generalmente se usan en las cabeceras de las funciones para expresar condiciones de entrada. Para ello se usa la palabra clave `when`. Son expresiones que devuelven un booleano.

```elixir
def example(number) when number>0, do: true
```

## 1.1.Guardas comunes
Normalmente se usan las funciones:
+ [>] `is_integer/1`, `is_list/1`, `is_nil/1`, etc.
+ [>]  `==`, `===`, `>`, `<=`, etc.
+ [>] `and/2`, `or/2` y `not/1`
+ [>] `in/2`

# 2.Definición de guardas
Se pueden definir guardas propias utilizando `defguard`. Por convención suelen empezar por `is_`.

```elixir
defmodule HTTP do 
	defguard is_success(code) when code >= 200 and code < 300 
	def handle_response(code) when is_success(code), do :ok
end
```