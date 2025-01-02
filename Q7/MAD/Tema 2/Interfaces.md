[[Tema 2-El lenguaje CSharp]]

## Cómo funcionan las interfaces?
Son similares a la definición de un contrato. Definen métodos, propiedades o eventos. No permiten campos, operadores, constructores y destructores. Las cosas definidas deben ser `public abstract` y ser implementadas en todas las implementaciones de la interfaz. 

Proporcionan polimorfismo, ya que múltiples clases o estructuras pueden implementar la misma interfaz. 

```CSharp
public interface ILimpiador {
	void Barrer();
	void Fregar();
}

public class Limpiador : ILimpiador {

	public void Barrer() {
		Console.WriteLine("Barriendo...");
	}

	public void Fregar() {
		Console.WriteLine("Fregando...");
	}
}
```