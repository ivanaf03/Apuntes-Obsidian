[[Elixir]]

Ejercicios asociados:
+ [[Top secret]]
+ [[DOT DSL]]

# 1.Definición
Un Abstract Syntax Tree es una forma de representar código como datos. Cada nodo es una tupla de tres elementos. 

```elixir
# 2+3

{:+, [], [2, 3]}
```

El primer elemento es un átomo con la operación, el segundo es una keyword list con los metadatos y el último argumento es una lista de argumentos, que puede contener otros nodos.

## 1.1.Transformaciones a AST
Los módulos `Code` y `Macro` permiten trabajar con AST. Por ejemplo, para pasar una String a AST. 

Otra forma de pasar directamente código a AST es con `quote`.

```elixir
quote do 
	2 + 3 - 1 
end 

# => {:-, [], [{:+, [], [2, 3]}, 1 ]}
```