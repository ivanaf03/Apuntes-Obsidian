[[Tema 2-El lenguaje CSharp]]

## Qué son los structs?
Los structs son un tipo especial de clases mucho más ligeras. Son un tipo de dato que se pasan por valor. A diferencia de las clases, no permiten herencia, pero si pueden implementar interfaces. 

```CSharp
public struct Point {

	public int x, y;
	
	public Point(int x, int y) {
		this.x = x;
		this.y = y;
	}
}
```

## Qué son los enums?
Son otro tipo de estructura formados por constantes públicas y estáticas. Por defecto son de tipo `int`, pero esto se puede cambiar por cualquier otro tipo básico que permita representar un entero. Se les puede dar valor, pero sino se hace, el compilador les da valores incrementales que empiezan en 0.

Permiten evitar los números mágicos y mejoran la legibilidad del código.

```CSharp
enum Semaphore {RED, GREEN, YELLOW}

public enum FontSize : int {
	SMALL: 12,
	NORMAL: 16,
	HUGE: 20
}
```
