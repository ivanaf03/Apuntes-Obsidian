[[Tema 2-El lenguaje CSharp]]

## Uso de namespaces
Los namespaces se usan para organizar y agrupar bien el código y evitar conflictos de nomenclatura. Por ejemplo:

```CSharp
namespace Empresa.Producto.Modulo {
    class MiClase {
        // doSomething
    }
}

Empresa.Producto.Modulo.MiClase miObjeto = new Empresa.Producto.Modulo.MiClase();
```

Para referenciar clases o tipos que estén fuera del namespace se usa `using` para evitar escribir todo el namespace. 

```CSharp
using Empresa.Producto.Modulo;

class Programa {
    static void Main() {
        MiClase miObjeto = new MiClase();
    }
}

```

Para recortar más todavía la sintaxis se pueden usar alias.

```CSharp
using MiModulo = Empresa.Producto.Modulo;

class Programa {
    static void Main() {
        MiModulo.MiClase miObjeto = new MiModulo.MiClase();
    }
}

```