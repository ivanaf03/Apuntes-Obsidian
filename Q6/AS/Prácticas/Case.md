[[Elixir]]

Ejercicios asociados:
+ [[German sysadmin]]
+ [[Protein translation]]
+ [[Grep]]

# 1.Definición
Es una estructura que permite comparar un valor dado con ciertos patrones. Las cláusulas se evalúan de arriba a abajo hasta que hacen match con una. Permite el uso de guardas.

```elixir
#Con case
def age_group(age) do
  case age do
    0 -> "infant"
    age when age < 4 -> "baby"
    age when age < 13 -> "child"
    age when age < 18 -> "teenager"
    _ -> "adult"
  end
end

#Con cláusulas
def age_group(0), do: "infant"
def age_group(age) when age < 4, do: "baby"
def age_group(age) when age < 13, do: "child"
def age_group(age) when age < 18, do: "teenager"
def age_group(_), do: "adult"
```
