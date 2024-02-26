[[Elixir]]

Ejercicios asociados:
+ [[Take a number]]
+ [[Bank account]]

# 1.Procesos
Un proceso en elixir cuenta con su identificador propio. Se llama PID (process identifier). Los PID son un tipo de datos propio. Para obtener el PID del proceso actual podemos usar `self()`.

Podemos comprobar si una variable es un PID con `is_pid/1`.

```elixir
pid = self()

if is_pid(pid) do
  IO.puts("El valor #{inspect(pid)} es un PID válido.")
else
  IO.puts("El valor #{inspect(pid)} NO es un PID válido.")
end

```

Normalmente los PID se generan automáticamente mediante funciones como `spawn` que crean un proceso. Si tenemos el PID de un proceso, podremos enviarle un mensaje.