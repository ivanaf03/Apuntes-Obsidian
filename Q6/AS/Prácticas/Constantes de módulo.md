[[Elixir]]

Ejercicios asociados:
+ [[High score]]
+ [[Space age]]
+ [[Kindergarten garden]]
+ [[Say]]
+ [[Scale generator]]

# 1.Constantes en elixir
Los atributos de módulo son constantes que se evalúan en tiempo de compilación. Se denotan con `@` y un nombre.

```elixir
defmodule Mod do
	@cons 5

	def five(), do: @cons
end
```

Pueden ser sobrescritos en el módulo.

```elixir
defmodule Mod do
	@cons 5
	@cons 10

	def ten(), do: @cons
end
```
