[[Elixir]]

```elixir
defmodule FlattenArray do
  @doc """
    Accept a list and return the list flattened without nil values.

    ## Examples

      iex> FlattenArray.flatten([1, [2], 3, nil])
      [1,2,3]

      iex> FlattenArray.flatten([nil, nil])
      []

  """

  @spec flatten(list) :: list
  def flatten(list) do
    list = List.flatten(list)
    flatten_in(list, [])
  end

  defp flatten_in(list, acc) when list==[], do: Enum.reverse(acc)
  defp flatten_in(list, acc) do
    [h|t] = List.flatten(list)
    if h == nil do
      flatten_in(t, acc)
    else
      flatten_in(t, [h | acc])
    end
  end
end

```