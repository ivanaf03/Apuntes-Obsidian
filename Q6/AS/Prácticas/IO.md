[[Elixir]]

Ejercicios asociados:
+ [[RPG character sheet]]

# 1.Entrada y salida
Para manejar las interacciones con el usuario podemos usar el módulo `IO`. 

```elixir
# Utilizando IO.puts/2 para escribir una cadena en la salida estándar seguida de un salto de línea
IO.puts("Hola Mundo")

# Utilizando IO.write/2 para escribir una cadena en la salida estándar sin agregar un salto de línea
IO.write("Hola ")

# Utilizando IO.write/2 nuevamente para escribir otra cadena en la misma línea
IO.write("Mundo")

# Utilizando IO.puts/2 para agregar un salto de línea al final
IO.puts("")

# Utilizando IO.gets/2 para leer una línea desde la entrada estándar y asignarla a una variable
nombre = IO.gets("Por favor, ingresa tu nombre: ")

# Utilizando IO.inspect/2 para imprimir el valor de la variable nombre con una etiqueta para depuración
IO.inspect(nombre, label: "Nombre ingresado")
```

## 1.1.Debug
Podemos usar IO.inspect para ver los valores de las variables a lo largo del código, a modo de debug.

```elixir
"HELLO\n" 
|> String.trim() 
|> IO.inspect(label: "step 1") 
|> String.downcase() 
|> IO.inspect(label: "step 2") 

# > step 1: "HELLO" 
# > step 2: "hello" 
# => "hello"
```