[[Elixir]]

# Átomos
Un átomo es una constante fija. Proporcionan seguridad a la hora de interactuar con los datos. Se escribe con : delante.
```elixir
variable= :atom
```

Internamente, los átomos están representados por un entero en una tabla de búsqueda, que se establece automáticamente. No es posible cambiar este valor interno.

# Cond
La función `cond/1` sirve para evaluar condiciones. Funciona similar al switch. 
```elixir
puntaje = 85

calificacion = cond do
  puntaje >= 90 -> :excelente
  puntaje >= 80 -> :bueno
  puntaje >= 70 -> :satisfactorio
  puntaje >= 60 -> :suficiente
  true -> :insuficiente
end

IO.puts("La calificación del estudiante es #{calificacion}.")
```

`true` es la cláusula por defecto.