[[Tema 7-Test project]]

## Qué es Test Project?
.NET tiene un tipo específico para crear y automatizar la realización de pruebas, el Test Project. Permite añadir plantillas para realizar pruebas unitarias.

```csharp
public class UnitTest1
{
    public UnitTest1()
    {
        //
        // TODO: Agregar aquí la lógica del constructor
        //
    }

    private TestContext testContextInstance;

    #region Atributos de prueba adicionales
    //
    // Puede usar los siguientes atributos adicionales conforme escribe las pruebas:
    //
    // Use ClassInitialize para ejecutar el código antes de ejecutar la primera prueba en la clase
    // [ClassInitialize()] 
    // public static void MyClassInitialize(TestContext testContext) { }
    //
    // Use ClassCleanup para ejecutar el código una vez ejecutadas todas las pruebas en una clase
    // [ClassCleanup()]
    // public static void MyClassCleanup() { }
    //
    // Usar TestInitialize para ejecutar el código antes de ejecutar cada prueba
    // [TestInitialize()]
    // public void MyTestInitialize() { }
    //
    // Use TestCleanup para ejecutar el código una vez ejecutadas todas las pruebas
    // [TestCleanup()]
    // public void MyTestCleanup() { }
    //
    #endregion
}
```

### Estructuras de Test Project
Trae las siguiente estructuras para colocar sobre los métodos y clases:
+ **\[TestClass]:** marca una clase que contiene métodos de prueba.
+ **\[TestMethod]:** marca un caso de prueba.
+ **\[ClassInitialize()]:** permite ejecutar métodos antes de ejecutar las pruebas de una clase de prueba.
+ **\[ClassCleanup()]:** permite ejecutar métodos después de ejecutar todas las pruebas. Se suele usar para liberar recursos.
+ **\[TestInitialize()]:** permite ejecutar métodos antes de cada una de las pruebas.
+ **\[TestCleanup()]:** permite ejecutar métodos después de cada una de las pruebas.
+ **\[ExpectedException(typeof(\<Exception>))]:** marca un método que lanza una excepción concreta. Si no la lanza, falla.

### Aserciones
Para definir como acaban las pruebas se hacen aserciones que evalúan si el resultado obtenido es el resultado esperado. Test Project incorpora:
+ AreEqual y AreNotEqual.
+ AreSame y AreNotSame.
+ IsTrue y IsFalse.
+ isNull y isNotNull.
+ isInstanceOfType y isNotInstanceOfType.
+ Fail.
+ Inconclusive.

## Ejemplo: Tests en MiniBank

```csharp
public class TestManager
{
    /// <summary>
    /// Configures and populates the Ninject kernel
    /// </summary>
    /// <returns>The NInject kernel</returns>
    public static IKernel ConfigureNInjectKernel()
    {
        NinjectSettings settings = new NinjectSettings() { LoadExtensions = true };
        IKernel kernel = new StandardKernel(settings);
        // Configuration code here...
        return kernel;
    }

    public static void ClearNInjectKernel(IKernel kernel)
    {
        kernel.Dispose();
    }
}

----------

// Use ClassInitialize to run code before running the first test in the class
[ClassInitialize()]
public static void MyClassInitialize(TestContext testContext)
{
    kernel = TestManager.ConfigureNInjectKernel();
    userProfileDao = kernel.Get<IUserProfileDao>();
}

// Use ClassCleanup to run code after all tests in a class have run
[ClassCleanup()]
public static void MyClassCleanup()
{
    TestManager.ClearNInjectContainer(container);
}

// Use TestInitialize to run code before running each test
[TestInitialize()]
public void MyTestInitialize()
{
    transaction = new TransactionScope();
}

// Use TestCleanup to run code after each test has run
[TestCleanup()]
public void MyTestCleanup()
{
    transaction.Dispose();
}

...

[TestMethod()]
public void CreateAccountTest()
{
    Account actual = new Account();
    actual.usrId = userId;
    actual.balance = balance;

    actual = accountService.CreateAccount(actual); // Establish idAccount
    Account expected = accountService.FindAccount(actual.accId);

    Assert.AreEqual(expected.usrId, actual.usrId);
    Assert.AreEqual(expected.balance, actual.balance, delta);
}

/// <summary>
/// Try to withdraw money from a non-existent account
/// </summary>
[TestMethod()]
[ExpectedException(typeof(InstanceNotFoundException))]
public void WithdrawFromNonExistentAccountTest()
{
    accountService.WithdrawFromAccount(NON_EXISTENT_ACCOUNT_ID, 10);
}
```