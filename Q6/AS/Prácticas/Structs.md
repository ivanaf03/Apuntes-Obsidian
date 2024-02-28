[[Elixir]]

Ejercicios asociados:
+ [[Remote control car]]
+ [[D&D character]]
+ [[Matrix]]
+ [[Clock]]
+ [[Robot simulator]]
+ [[Queen attack]]
+ [[Bowling]]
+ [[Zipper]]

# 1.Definición
Los structs son unas estructuras basadas en mapas que dan valores por defecto y comprobaciones en tiempo de compilación. Para definirlos se utiliza `defstruct`. Aceptan átomos o keyword lists.

```elixir
defmodule User do
  defstruct name: "", age: 0, email: ""
end

# Crear una instancia de la estructura User
user = %User{name: "John", age: 30, email: "john@example.com"}

# Acceder a los campos de la estructura
IO.puts("Nombre: #{user.name}")
IO.puts("Edad: #{user.age}")
IO.puts("Email: #{user.email}")

# Actualizar un campo de la estructura
updated_user = %{user | age: 31}

IO.puts("Edad actualizada: #{updated_user.age}")
```

## 1.1.Valores obligatorios
Podemos hacer que un valor sea obligatorio mediante `@enforce_keys`. Al crear un struct esos valores serán obligatorios.

```elixir
defmodule User do
  @enforce_keys [:name, :age]  # Indicamos que los campos :name y :age son obligatorios
  
  defstruct [:name, :age, :email]  # Definimos la estructura con los campos name, age y email
end

# Intentamos crear una instancia de la estructura sin especificar los campos obligatorios
user = %User{}  # Esto generará un error ya que no se han especificado los campos obligatorios

```