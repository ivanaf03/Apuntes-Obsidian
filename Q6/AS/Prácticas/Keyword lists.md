[[Elixir]]

Ejercicios asociados:
+ [[Wine cellar]]
+ [[DOT DSL]]

# 1.Definición
Una keyword list es una lista de pares clave-valor.  Las claves tienen que ser átomos. Se pueden escribir de dos maneras.

```elixir
# forma simple
[month: "April", year: 2018]

# forma explícita
[{:month, "April"}, {:year, 2018}]
```

Se puede entrecomillar un átomo para usar espacios, por ejemplo. Pero no por eso es una string, sigue siendo un átomo.

```elixir
Keyword.keyword?(["day of week": "Monday"])  # true
```

Las claves pueden repetirse. En caso de buscar un valor para esa clave, devolverá el primero.

```elixir
list = [month: "April", month: "May"]

Keyword.get_values(list, :month)  # ["April", "May"]

Keyword.get(list, :month)  # "April"
```

Soportan access behavior.

```elixir
list[:month]  # "April"
```

## 1.1.Argumentos de función
Suele ser muy común pasarle como argumentos a las funciones keyword lists. Elixir permite eliminar los corchetes cuando el último argumento de una función es una keyword list.

```elixir
defmodule Saludos do
  def saludar(nombre, opciones \\ []) do
    default = %{saludo: "Hola", emoticon: "😊"}  # Opciones predeterminadas
    opciones = Keyword.merge(default, opciones)
    mensaje = "#{opciones[:saludo]} #{nombre} #{opciones[:emoticon]}"
    IO.puts(mensaje)
  end
end

# Llamada a la función con opciones usando corchetes
Saludos.saludar("Juan", [saludo: "Hola", emoticon: "👋"])

# Llamada a la función con opciones sin corchetes
Saludos.saludar("Maria", saludo: "Hola", emoticon: "👋")

```

## 1.2.Pattern matching
No es recomendable el uso de pattern matching. Para hacerlo es necesario poner todas las claves y que estén en orden. Es mejor usar el módulo `Keyword` o el access behavior.

```elixir
[month: month] = [month: "April", year: 2018]  # error

[year: year, month: month] = [month: "April", year: 2018]  # error
```

## 1.3.Keyword lists vs mapas

Aquí tienes la información proporcionada en forma de tabla Markdown:

Por supuesto, aquí tienes la tabla en español:

|                   | Keyword list                 | Mapa                                          |
| ----------------- | ---------------------------- | --------------------------------------------- |
| Tipo de clave     | Átomos                       | Cualquier tipo, puede ser mezclado en un mapa |
| Claves duplicadas | Sí                           | No                                            |
| Claves ordenadas  | Sí                           | No                                            |
| Acceso            | lista[:clave], Keyword.get/2 | mapa.clave, mapa[:clave], Map.get/2           |
| Tiempo de acceso  | Lineal                       | Logarítmico                                   |
| Pattern matching  | No muy útil                  | Útil                                          |
