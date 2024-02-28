[[Elixir]]

```elixir
defmodule TopSecret do
  def to_ast(string) do
    {_, code} = Code.string_to_quoted(string)
    code
  end

  def decode_secret_message_part(ast={a, _, [{:when, _, [{a1, _, a3} | _]}, _]}, acc) when a in [:def, :defp] do
    {ast,  [String.slice(to_string(a1), 0, length(a3 || [])) | acc]}
  end

  def decode_secret_message_part(ast={a, _, [{a1, _, a3}|_]}, acc) when a in [:def, :defp] do
    {ast,  [String.slice(to_string(a1), 0, length(a3 || [])) | acc]}
  end

  def decode_secret_message_part(ast, acc)do
    {ast, acc}
  end

  def decode_secret_message(string) do
    string
    |> to_ast()
    |> Macro.prewalk([], &decode_secret_message_part/2)
    |> elem(1)
    |> Enum.reverse()
    |> Enum.join("")
  end
end

```