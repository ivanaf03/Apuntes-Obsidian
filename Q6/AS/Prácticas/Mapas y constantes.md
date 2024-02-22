[[Elixir]]

# Mapas
Son estructuras de datos que guardan información en pares clave-valor. Pueden ser de cualquier tipo de dato, pero si la clave es un átomo se puede usar sintaxis propia. 

```elixir
# Añadir valor a una clave que es un átomo
%{atom_key: 1}

# Añadir valor a una clave de distinto tipo:
%{1 => :atom_value}
```

# Constantes
Podemos definir constantes de módulo para usar en las funciones del módulo. Se hace con `@`.
```elixir
defmodule Example do
	@constant_number 1
	
	def example_value() do
		@constant_number 
	end
end
```