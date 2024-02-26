[[Elixir]]

```elixir
defmodule TakeANumber do
  def start do
    spawn(fn ->loop(0) end)
  end

  defp loop(current_number) do
    receive do
      {:report_state, sender_pid} ->
        send(sender_pid, current_number)
        loop(current_number)
      {:take_a_number, sender_pid} ->
        send(sender_pid, current_number+1)
        loop(current_number+1)
      :stop -> :ok
      _ -> loop(current_number)
    end
  end
end

```