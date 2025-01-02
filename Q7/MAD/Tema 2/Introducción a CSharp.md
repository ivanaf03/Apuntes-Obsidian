[[Tema 2-El lenguaje CSharp]]

## Qué es C#?
Es un lenguaje de programación orientado a objetos que se puede utilizar para desarrollar aplicaciones en .NET. El objetivo es reducir el tiempo de desarrollo, evitando detalles de programación de bajo nivel.

En C# todo es un objeto, por tanto, todo hereda de `System.Object`, aunque también permite declarar tipo primitivos que pueden, si es necesario, ser transformados en objetos.

### Convenciones
Por convención, los métodos y nombres de clases se ponen en PascalCase. Los atributos se ponen en camelCase. C# es sensible a mayúsulas.

## Hola mundo en C#
```CSharp
using System;

namespace Es.Udc.DotNet.CSharpTutorial {

	class HelloWorld {
	
		public static void Main(){
			Console.WriteLine("Hello world!");
		}
		
	}
}
```

El Main puede recibir parámetros. Acepta un array de argumentos `Main(string args[])`.

## Jerarquía de clases
Funciona igual que Java. Solo admite herencia simple, pero permite la implementación de múltiples interfaces. 

### System.Object
El la clase de la que heredan todas las clases en C#. Define las interfaces de los métodos:

```CSharp
public class Object { 
	public Object(); 
	
	public virtual bool Equals(object obj); 
	public static bool Equals(object objA, object objB); 
	public virtual int GetHashCode(); 
	public Type GetType(); 
	protected object MemberwiseClone();
	public static bool ReferenceEquals(object objA, object objB);
	public virtual string ToString();
}
```

Esto permite que cualquier clase pueda sobrescribirlos:

```CSharp
public override bool Equals(object obj) {
	Car car = (Car) obj;

	return (this.Doors == car.Doors) && (this.Wheels == car.Wheels);
}
```



