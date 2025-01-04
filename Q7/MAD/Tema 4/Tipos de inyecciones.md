[[Tema 4-Inyección de dependencias con Ninject]]

## Tipos
Los 2 tipos más frecuentemente usados son:
+ Propiedad.
+ Constructor con parámetros.

### Inyección de propiedad

```csharp
using Ninject;

namespace Es.Udc.DotNet.MiniBank.Model.AccountService
{
    public class AccountService : IAccountService
    {
        [Inject]
        public IAccountDao AccountDao { private get; set; }

        [Inject]
        public IAccountOperationDao AccountOperationDao { private get; set; }

        // Métodos y lógica adicional
        ...
    }
}

----------

// Instanciación del servicio mediante el kernel de Ninject
IKernel kernel = new StandardKernel();
IAccountService accountService = kernel.Get<IAccountService>();

```

### Inyección de constructor con parámetros

```csharp
public class DbContext
{
    private String connectionString;

    public String ConnectionString { get; private set; }

    public DbContext(String nameOrConnectionString)
    {
        ...
    }

    ...
}

----------

// Configuración de Ninject
string connectionString = ConfigurationManager.ConnectionStrings["MiniBankEntities"].ConnectionString;

IKernel kernel = new StandardKernel();

kernel.Bind<DbContext>()
      .ToSelf()
      .InSingletonScope()
      .WithConstructorArgument("nameOrConnectionString", connectionString);
```

