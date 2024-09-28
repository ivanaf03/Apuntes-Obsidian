[[Tema 2-El lenguaje CSharp]]

## Qué es C#?
Es un lenguaje de programación orientado a objetos para desarrollar aplicaciones en .NET. Busca reducir el tiempo de desarrollo evitando detalles de programación de bajo nivel.

Para C# todo es un objeto, incluso los tipos primitivos. Permite el uso de mecanismos de boxing y unboxing, que es la conversión de tipos primitivos a objetos y viceversa.
$\space$
### Nomenclatura
Los métodos y nombres de clases se ponen en PascalCase, ya que es sensible a mayúsculas y minúsculas. Los atributos se ponen en camelCase. 
$\space$
## Hola mundo
```CSharp
using System; //librería que incluye clases básicas, como Console

namespace Es.Udc.DotNet.CSharpTutorial { // espacio de nombres para evitar conflictos
    /*
    * Class HellowWorld
    * Description: simple C# example
    */
    class HelloWorld {
        public static void Main() {
            Console.WriteLine("Hello World!");
            Console.ReadLine();
        }
    }
}
```
$\space$
## Jerarquía de clases
Solo admite herencia simple, como Java. También es idéntico en que sí permite implementación de múltiples interfaces. 
$\space$
### System.Object
Todos los tipos heredan de `System.Object`. 

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

Todos los métodos de `System.Object` se pueden sobrescribir. Por ejemplo:

```CSharp
public override bool Equals(object obj) {
	UserProfileDetails target = (UserProfileDetails)obj; 
	
	return (this.FirstName == target.FirstName) && (this.Lastname == target.Lastname) && (this.Email == target.Email) && (this.Language == target.Language) && (this.Country == target.Country); 
}
```



