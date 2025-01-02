[[Tema 2-El lenguaje CSharp]]

## Cómo se declaran las clases?
Las clases de C# son muy parecidas a las de Java. Están formadas por constructores, destructores, campos, propiedades y métodos.

### Constructores
Todas las clases tienen constructor, aunque no es obligatorio definirlo. El constructor por defecto no contiene parámetros y lo genera el compilador automáticamente. Los constructores no se pueden heredar, sin embargo, al instanciar una clase hija, primero se llama al constructor sin parámetros del padre y después se llama al de la hija.

Para llamar a otro constructor de la clase padre cuando ocurre esto se puede usar el inicializador `base`. Otro inicializador es `this`, que permite llamar a constructores de la misma clase para realizar sobrecargas.

```CSharp
using System;

class SuperClass
{
    private string argument1;

    // Constructor sin parámetros, llama al constructor con parámetro
    public SuperClass() : this("<Default arg1>") { }

    // Constructor con un parámetro
    public SuperClass(string arg1)
    {
        this.argument1 = arg1;
        Console.WriteLine("Arguments: " + argument1);
    }

    public static void Main()
    {
        // Creando una instancia de SuperClass
        SuperClass sc = new SuperClass(); 
        // Muestra: Arguments: <Default arg1>

        // Crear una instancia de ChildClass sin parámetros
        ChildClass cc = new ChildClass(); 
        // Muestra: Arguments: <Default arg2>

        // Crear una instancia de ChildClass con dos parámetros
        ChildClass cc2 = new ChildClass("1", "2");
        // Muestra: Arguments: 1
        // Muestra: Arguments: 2

        Console.ReadLine();
    }
}

class ChildClass : SuperClass
{
    private string argument2;

    // Constructor sin parámetros, llama al constructor con un parámetro
    public ChildClass() : this("<Default arg2>") { }

    // Constructor con un parámetro
    public ChildClass(string arg2)
    {
        this.argument2 = arg2;
        Console.WriteLine("Arguments: " + argument2);
    }

    // Constructor con dos parámetros, llama al constructor de la clase base
    public ChildClass(string arg1, string arg2)
        : base(arg1)  // Llama al constructor de SuperClass con el primer argumento
    {
        this.argument2 = arg2;
        Console.WriteLine("Arguments: " + argument2);
    }
}
```

### Constructores estáticos
Si se declara un constructor estático, se puede inicializar código antes de crear la instancia de la clase. Permite acceder a cualquier miembro estático de la clase. 

Solo puede haber uno por clase. No permiten parámetros.

```CSharp
using System;
using System.IO;

public class LogManager
{
    private static FileStream logFile;

    static LogManager()
    {
        logFile = File.Open("logFile.dat", FileMode.Create);
    }

    public LogManager()
    {
        StreamWriter writer = new StreamWriter(logFile);
        writer.WriteLine(System.DateTime.Now.ToString() + " Instance created");
        writer.Flush();
    }
}
```

### Destructores
Los destructores son métodos que el recolector de basura llama automáticamente cuando ya no existen referencias a ese objeto. No pueden heredarse.

```CSharp

~LogManager()
{
	if (logFile != null)
	{
		logFile.Close(); // Cierra el archivo
		Console.WriteLine("logFile cerrado en el destructor.");
	}
}
```

### Campos constantes
Las constantes de clase se evalúan en tiempo de compilación. Se definen con `const` y son estáticas por defecto. Tienen que inicializarse al ser declaradas.

```CSharp
public const int NUMBER = 1;
```

Se puede acceder a ellas desde código externo, por ejemplo `NumberClass.NUMBER`.

### Campos de solo lectura
Otros campos que funcionan de forma muy similar a las constantes son los valores de solo lectura. Sin embargo, se inicializan en tiempo de ejecución, por lo que pueden ser tanto estáticas como ser inicializadas en un constructor. Una vez inicializadas, no pueden modificarse.

```CSharp
public readonly int NUMBER;
public static readonly int NUMBER2 = 2;

public NumberClass () {
	NUMBER = 1;
}
```

### Propiedades
Normalmente, en las clases se declaran los atributos como privados y se definen los getter y setter necesarios. Sin embargo, en .NET se pueden encapsular mediante un mecanismo llamado properties.

```CSharp
public class Person
{
    private string name;  // property compleja

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public int Age { get; set; }  // property simple
}
```

Se puede acceder a ellas como si fueran un campo público, sin necesidad de usar el getter y el setter, por ejemplo, `person1.Age = 20`.

Pueden construirse properties de solo lectura utilizando `private`.

```CSharp
public class Person
{
    private string name;

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public int Age { private get; set; }  // no se puede saber la edad
}
```

Se pueden definir properties en interfaces o en clases abstractas, declarando estas también como abstractas.

### Métodos
Por defecto los métodos en C# son `sealed`, no se pueden sobrescribir. Para poder redefinir un método debe ser `virtual` y en la redefinición se debe invocar a `override`.

```CSharp
public class Product {

	public virtual String GetRef() {
		return barCode;
	}
	
}

public class Book : Product {

	public override String GetRef() {
		return ISBN;
	}

}
```

## Clases abstractas
> [!abstract] Definición de clase abstracta
> Una clase abstracta es aquella que fuerza a que se derive en clases hijas para permitir su instanciación.

Permiten declarar métodos que no se definen directamente en su implementación, pero fuerzan a las clases hijas a implementarlos. No son obligatorios, pero si se definen, la clase tiene que definirse obligatoriamente como abstracta. Los métodos `abstract` son `virtual` por defecto.

```CSharp
public abstract class Animal
{
    public abstract void MakeSound();
}

public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Woof!");
    }
}
```

## Clases sealed
> [!abstract] Definición de clase sealed
> Una clase sealed es aquella que no permite ser extendida.

```CSharp
public sealed class Car
{
    public string Make { get; set; }
    public string Model { get; set; }

    public void Start()
    {
        Console.WriteLine("Car started.");
    }
}
```

