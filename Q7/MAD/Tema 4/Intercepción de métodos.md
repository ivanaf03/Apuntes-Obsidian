[[Tema 4-Inyección de dependencias con Ninject]]

## Programación orientada a aspectos
> [!abstract] Definición de POA
> La programación orientada a aspectos es un paradigma que busca separar las partes que afectan a la mayoría de la aplicación, como la gestión de transacciones, el sistema de logs, la seguridad, etc.

Ninject proporciona POA a través del plugin de `Ninject.Extensions.Interception`. Ayuda con la gestión de transacciones interceptando llamadas a métodos, es decir, analiza el contenido de las llamadas y decide si debe modificar su comportamiento.

## Tipos de intercepción
La intercepción puede ser:
+ Mediante miembros o propiedades.
+ Mediante tipos.
+ Mediante atributos.

### Intercepción mediante miembros o propiedades
Se utilizan los métodos `InterceptReplace()`, `InterceptAround()`, `InterceptBefore()` y `InterceptAfter()`. Por ejemplo:

```csharp
Kernel.InterceptAround<AccountService>(
    s => s.GetAllAccounts(),
    invocation => logger.Info("Retrieving all accounts..."),
    invocation => logger.Debug("Accounts retrieved")
);

Kernel.InterceptAfter<AccountService>(
    s => s.GetAllAccounts(),
    invocation => logger.DebugFormat(
        "Total {0} accounts retrieved",
        ((IEnumerable)invocation.ReturnValue).Cast<object>().Count()
    )
);
```

### Intercepción mediante tipos
El tipo debe implementar la interfaz `IInterceptor`, que contiene el método `Intercept()`. Por ejemplo:

```csharp
kernel.Bind<IAccountService>()
      .To<AccountService>()
      .Intercept()
      .With<ExceptionInterceptor>();
```

### Intercepción mediante atributos
Se puede definir un atributo `[Transactional]` para hacer que un método sea transaccional de una forma mucho más legible que haciéndolo de la forma tradicional. 

```csharp
using Ninject;
using Ninject.Extensions.Interception;
using Ninject.Extensions.Interception.Attributes;
using Ninject.Extensions.Interception.Request;

namespace Es.Udc.DotNet.ModelUtil.Transactions
{
    /// <summary>
    /// Defines the Attribute [Transactional] to use it as interceptor for
    /// transactional methods.
    /// </summary>
    /// <seealso cref="Ninject.Extensions.Interception.Attributes.InterceptAttribute" />
    public class TransactionalAttribute : InterceptAttribute
    {
        public override IInterceptor CreateInterceptor(IProxyRequest request)
        {
            return request.Kernel.Get<TransactionalInterceptor>();
        }
    }
}

----------

[Transactional]
void sayHello() {
	Console.WriteLine("Hello!");
}
```

El `TransactionalInterceptor()` es una implementación del método `Intercept()`. Realiza en una transacción llamando al método transaccional mediante `invocation.Proceed()`.