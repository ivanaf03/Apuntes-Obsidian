[[Elixir]]

Ejercicios asociados:
+ [[Community garden]]
+ [[Bank account]]

# 1.Definición
El módulo `Agent` permite abstraerse al hacer procesos y bucles de envío y recepción. Para empezar un proceso agente utilizamos la función `start/2`. La función pasada como argumento devuelve el estado inicial del proceso.

```elixir
defmodule ExampleAgent do
  def start_link(initial_state) do
    Agent.start_link(fn -> initial_state end)
  end

  def get_state(agent) do
    Agent.get(agent, & &1)
  end

  def update_state(agent, new_state) do
    Agent.update(agent, fn _ -> new_state end)
  end
end

# Uso del agente
{:ok, agent} = ExampleAgent.start_link(%{count: 0})

# Obtener el estado inicial
state = ExampleAgent.get_state(agent)
IO.puts("Estado inicial: #{inspect(state)}")

# Actualizar el estado
new_state = %{state | count: state.count + 1}
ExampleAgent.update_state(agent, new_state)

# Obtener el estado actualizado
updated_state = ExampleAgent.get_state(agent)
IO.puts("Estado actualizado: #{inspect(updated_state)}")

```