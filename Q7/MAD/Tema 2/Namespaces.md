[[Tema 2-El lenguaje CSharp]]

## Uso de namespaces
> [!abstract] Definición de namespace
> Los namespaces son una jerarquía que se utiliza para agrupar y organizar el código para evitar conflictos de nomenclatura.

Pueden anidarse para mayor semántica y jerarquización. Se puede hacer referencia a ellos mediante `using`.

```CSharp
namespace Worker.Tech {

	class Engineer {
	
		public static string SayHello(){
			return "Hi! I am the engineer.";
		}
		
	}
}

----------

using Worker;

namespace Work {

	class Order {
		
		public string PresentWorkers(){
			Tech.Engineer.SayHello();
		}

	}
}
```

### Alias
Se puede simplificar el uso de namespaces mediante alias.

```CSharp
using WE = Worker.Tech.Engineer;

namespace Work {

	class Order {
		
		public string PresentWorkers(){
			WE.SayHello();
		}

	}
}
```
