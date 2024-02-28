[[Elixir]]

Ejercicios asociados:
+ [[File sniffer]]
+ [[Pig latin]]

# 1.Números binarios
Elixir permite trabajar de forma cómoda con binarios mediante las bitstrings. Los binarios son un tipo de bitstring con un número de bits divisible por ocho. Se debe a que un byte puede representar los números del 0 al 255.

Se definen con `<<>>`. Un valor fuera del rango de 0 a 255 falla. Se suelen representar en hexadecimal. El `<<0>>` es el binario nulo.

Por defecto llevan el modificador `::binary`asociado y se pueden concatenar con `<>`.

```elixir
<<255>> == <<0xFF>>

<<256>> == <<0>>

<<2, 4, 6, 8, 10, 12, 14, 16>> == <<0x02, 0x04, 0x06, 0x08, 0x0A, 0x0C, 0x0E, 0x10>>
```

## 1.1.Pattern matching
Al igual que con muchos otros tipos de datos, los binarios permiten pattern matching.

```elixir
defmodule ProcesadorMensaje do
  def extraer_cuerpo(<<_::binary-size(8), cuerpo::binary>>) do
    # Aquí puedes realizar cualquier procesamiento que necesites con el cuerpo del mensaje
    IO.puts("Cuerpo del mensaje: #{cuerpo}")
    # También podrías retornar el cuerpo del mensaje si lo necesitas para más procesamiento
    cuerpo
  end
end

# Supongamos que recibimos un mensaje binario de red
mensaje_binario = <<1, 2, 3, 4, 5, 6, 7, 8, 97, 98, 99, 100>>

# Llamamos a la función extraer_cuerpo para procesar el mensaje
ProcesadorMensaje.extraer_cuerpo(mensaje_binario)  # <<97, 98, 99, 100>>

```