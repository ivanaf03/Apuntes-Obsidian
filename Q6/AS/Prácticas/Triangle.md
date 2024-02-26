[[Elixir]]

```elixir
defmodule Triangle do
  @type kind :: :equilateral | :isosceles | :scalene

  defguardp is_triangle(a, b, c) when a > 0 and b > 0 and c > 0 and a + b >= c and b + c >= a and a + c >= b
  
  @doc """
  Return the kind of triangle of a triangle with 'a', 'b' and 'c' as lengths.
  """
  @spec kind(number, number, number) :: {:ok, kind} | {:error, String.t()}
  def kind(a, b, c) when is_triangle(a, b, c) do
    cond do
      a == b and b == c -> {:ok, :equilateral}
      a == b or b == c or a == c -> {:ok, :isosceles}
      true -> {:ok, :scalene}
    end
  end

  def kind(a, b, c) when a <= 0 or b <= 0 or c <= 0, do: {:error, "all side lengths must be positive"}  
  def kind(a, b, c) when a + b < c or b + c < a or a + c < b, do: {:error,  "side lengths violate triangle inequality"}
end

```