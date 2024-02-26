[[Elixir]]

Ejercicios asociados:
+ [[Guessing game]]
+ [[Yatch]]
+ [[All your base]]
+ [[Leap]]
+ [[Prime factors]]
+ [[Twelve days]]
+ [[OCR numbers]]
+ [[Robot simulator]]
+ [[Bowling]]
+ [[Bottle song]]
+ [[Ledger]]

# 1.Principio abierto-cerrado
Elixir facilita elPrincipio Abierto-Cerrado al permitir que las funciones tengan múltiples cláusulas, de modo que en lugar de tener una lógica de control dispersa y codificada de manera rígida, se pueden escribir funciones específicas para agregar o eliminar comportamientos fácilmente.

Las variables que no se usen se indican con una `_` delante.

```elixir
def number(n) when n == 7 do
  "Genial, ese es mi favorito"
end

def number(_n) do
  "Ese no es mi favorito"
end
```

## 1.1.Usos
Se suelen utilizar varias cláusulas para separar la lógica del cuerpo de las funciones. Se leen en orden, de arriba a abajo. Si ninguna coincide, se produce un error. 

```elixir
defmodule Mood do
  @spec mood_score(integer) :: String.t
  def mood_score(10), do: "¡Muy feliz!"
  def mood_score(7), do: "Feliz"
  def mood_score(8), do: "Feliz"
  def mood_score(5), do: "Neutral"
  def mood_score(6), do: "Neutral"
  def mood_score(3), do: "Triste"
  def mood_score(4), do: "Triste"
  def mood_score(1), do: "Muy triste"
  def mood_score(2), do: "Muy triste"
  def mood_score(score), do: "Puntaje inválido: #{score}. Debe estar entre 1 y 10."
end
```

# 2.Múltiples cláusulas en funciones anónimas
Las funciones anónimas también pueden tener múltiples cláusulas.
```elixir
fn 
	13 -> "Awesome, that's my favorite"
	 _ -> "That's not my favorite" 
end
```