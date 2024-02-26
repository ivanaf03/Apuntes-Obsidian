[[Elixir]]

Ejercicios asociados:
+ [[Log level]]
+ [[Darts]]
+ [[Zebra puzzle]]
+ [[Binary search]]
+ [[Bob]]
+ [[Perfect numbers]]
+ [[State os tic-tac-toe]]

# 1.Cláusula cond
La cláusula `cond` ejecuta la primera cláusula que sea cierta. Al menos una de ellas debe ser `true`. Se usa cuando hay demasiados `if` anidados. 

```elixir
cond do
	x > 10 -> :this_might_be_the_way 
	y < 7 -> :or_that_might_be_the_way 
	true -> :this_is_the_default_way
end
```

Cuando las condiciones caen sobre las mismas variables es más recomendable usar `case`.
```elixir
case rem(number, 2) do
	0 -> "Número par"
	 _ -> "Número impar"
end
```