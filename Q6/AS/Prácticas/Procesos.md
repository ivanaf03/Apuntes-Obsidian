[[Elixir]]

Ejercicios asociados:
+ [[Take a number]]
+ [[Circular buffer]]
+ [[React]]
+ [[Parallel letter frequency]]
+ [[Bank account]]

# 1.Procesos en elixir
Todos los códigos de elixir corren dentro de procesos. No son los mismos que los procesos del sistema. Permiten:
+ [>] Mantener un estado global.
+ [>] Contener los errores.
+ [>] Hacer códigos concurrentes y asíncronos.

## 1.1.Creación de procesos
Cuando queremos que una función se ejecute en un proceso concreto usamos `spawn`. Podemos hacerlo de dos formas:
+ [>] *Con 1 argumento:* la propia función.
+ [>] *Con 3 argumentos (MFA):* la función, el nombre de la función y una lista de argumentos.

```elixir
spawn(fn -> 2 + 2 end)
# => #PID<0.125.0>

spawn(String, :split, ["hello there", " "])
# => #PID<0.113.0>
```

El proceso termina cuando la función se ejecute. Podemos comprobar si está vivo el proceso con `Process.alive?/1`.

```elixir
pid = spawn(fn -> :timer.sleep(1000) end)  # Crea un nuevo proceso que espera 1 segundo

if Process.alive?(pid) do
  IO.puts("El proceso con PID #{inspect(pid)} está vivo.")
else
  IO.puts("El proceso con PID #{inspect(pid)} no está vivo.")
end
```

# 2.Mensajes
## 2.1.Envío de mensajes
Los procesos no comparten información entre ellos. Necesitan mensajes para compartir datos. Esto se llama patrón actor-model. Para enviarlos usamos `send/2`.

```elixir
send(pid, :hello)
```

`send` no comprueba que el mensaje haya llegado a su destino.  

## 2.2.Recepción
Puedes recibir mensajes enviados al proceso actual con `receive/1`. Funciona con pattern matching. 

Por defecto esperan de forma infinita, pero esto se puede evitar con un timeout utilizando `after`. Siempre debe haber una cláusula `_` para evitar esperas infinitas.

```elixir
receive do
  {:ping, sender_pid} -> send(sender_pid, :pong)
  _ -> nil
after
  5000 ->
    {:error, "No message in 5 seconds"}
end
```

Si queremos recibir más de un mensaje tenemos que llamar a `receive` de forma recursiva. 

```elixir
def loop(state) do
  receive do
    :increment_by_one ->
      loop(state + 1)
    {:report_state, sender_pid} ->
      send(sender_pid, state)
      loop(state)
    :stop ->
      nil
    _ ->
      loop(state)
  after
    5000 ->
      IO.puts("No message received in 5 seconds.")
  end
end
```