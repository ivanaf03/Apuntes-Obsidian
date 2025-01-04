[[Tema 4-Inyección de dependencias con Ninject]]

## Qué es Ninject?
Ninject es un contenedor que proporciona una forma sencilla de implementar el patrón de inversión de control y, como consecuencia de esto, el patrón de inyección de dependencias.

> [!abstract] Definición de inyección de dependencias
> El patrón de inyección de dependencias consiste en la extracción de dependencias a una clase posterior en lugar de hacer que esta las cree por sí misma.

### Dependencias
> [!abstract] Definición de dependencia
> Una dependencia es un objeto que necesita una clase para realizar un trabajo.

Los problemas de las dependencias es que mantienen el código demasiado acoplado, lo que complica los tests y el mantenimiento. 

## Extracción de dependencias
Existen dos alternativas típicas para evitar los problemas con las dependencias:
+ Delegación en factorías.
+ Contenedores de inyección de dependencias.

### Delegación en factorías
Las factorías leen de ficheros de configuración el nombre de la instancia que toque. 

```CSharp
public void RegisterUser(String loginName, String clearPassword, UserProfileDetailsVO userProfileDetailsVO)
{

    string comentarioInstance = ConfigurationManager.AppSettings["Comentario"];

	// Llamada a factorías
    DbConnection connection = dbProviderFactory.CreateConnection();
    IUserProfileDAO dao = UserProfileDAOFactory.GetDAO(comentarioInstance);


    String encryptedPassword = Crypto.crypt(clearPassword);
    UserProfileVO userProfileVO = new UserProfileVO(loginName, encryptedPassword, userProfileDetailsVO);

    dao.Create(connection, transaction, userProfileVO);
}
```

Sin embargo, este modelo sigue teniendo algunos problemas. Sigue siendo dependiente de la factoría y si se necesita la factoría en varios sitios puede haber mucho código duplicado para crear diferentes factorías.

### Contenedor de inyección de dependencias
Es otra opción más simple y que evade algunos problemas. Se programa un contenedor mediante interfaces de las clases que se necesitan inyectar y el contenedor inyecta las implementaciones de las interfaces.

```CSharp
public void RegisterUser(String loginName, String clearPassword, UserProfileDetailsVO userProfileDetailsVO)
{

	...
	
    IUserProfileDAO dao = kernel.Resolve<IUserProfileDAO>();

    String encryptedPassword = Crypto.crypt(clearPassword);
    UserProfileVO userProfileVO = new UserProfileVO(loginName, encryptedPassword, userProfileDetailsVO);

    dao.Create(connection, transaction, userProfileVO);
}
```

El contenedor almacena las referencias a las clases. Se puede configurar mediante código o mediante un XML de configuración. 

```CSharp
//Mediante código

IKernel kernel = new StandardKernel();

kernel.Bind<IAccountService>()
      .To<AccountService>();

string connectionString = 
	...

kernel.Bind<DbContext>()
      .ToSelf()
      .InSingletonScope()
      .WithConstructorArgument("nameOrConnectionString", connectionString);

```

```csharp
//Mediante archivos de configuración

<module name="myXmlConfigurationModule">
  <bind 
    service="Es.Udc.DotNet.MiniBank.Model.AccountService.IAccountService, MiniBank.Model" 
    to="Es.Udc.DotNet.MiniBank.Model.AccountService.AccountService, MiniBank.Model" 
  />
  <bind 
    service="Es.Udc.DotNet.MiniBank.Model.AccountDao.IAccountDao, MiniBank.Model" 
    to="Es.Udc.DotNet.MiniBank.Model.AccountDao.AccountDaoEntityFramework, MiniBank.Model" 
  />
  <bind 
    service="System.Data.Entity.DbContext, EntityFramework" 
    to="System.Data.Entity.DbContext, EntityFramework" 
  />
</module>

----------

NinjectSettings settings = new NinjectSettings() { LoadExtensions = true }; 

IKernel kernel = new StandardKernel(settings); 

kernel.Load("NInject_Config.xml");
```

## Contenedor de dependencias
El contenedor se debe crear al inicio de cada ejecución. Por ejemplo, en el archivo `Main.cs` o en el `Global.asax`. 


