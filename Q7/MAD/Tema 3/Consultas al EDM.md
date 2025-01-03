[[Tema 3-Implementación de persistencia con ADO.NET Entity Framework]]

## Formas de consultar el EDM
Existen varias formas de consultar el EDM:
+ Consultas Linq.
+ EntitySQL.
+ Mediante métodos especiales.
+ EntityClient.

Las dos formas más a alto nivel y más cómodas son las 2 primeras, aunque cualquier forma es válida. Una consulta podría ser:

```CSharp
static void Main(string[] args) 
{
    using (TestEntities context = new TestEntities()) 
    {
        DbSet accounts = context.Accounts;

        foreach (Account account in accounts) 
        {
            Console.WriteLine("Acc ID: {0}, Balance: {1}", account.accId, account.balance);
        }
    }
}
```

### Con Linq
Esta misma consulta se puede hacer con Linq y paginada.

```CSharp
using (TestEntities context = new TestEntities())
{
    List<Account> accounts = 
        (from a in context.Accounts
         where a.usrId == userId
         orderby a.accId
         select a)
        .Skip(startIndex)
        .Take(count)
        .ToList();

    foreach (Account account in accounts)
    {
        Console.WriteLine("Acc ID: {0}, Balance: {1}", account.accId, account.balance);
    }
}
```

La ventaja con respeto a EntitySQL es que permite un mayor nivel de abstracción. Además tiene tipado fuerte, el compilador en este caso ya sabe que `userId` existe en el modelo.

### Con EntitySQL
También se puede hacer con EntitySQL y paginada.

```CSharp
using (TestEntities context = new TestEntities())
{
    String query = "SELECT VALUE a FROM Accounts AS a " +
                   "WHERE a.usrId = @userId " +
                   "ORDER BY a.accId";

    ObjectParameter param = new ObjectParameter("userId", userId);

    List<Account> accounts = context.Database
                                     .SqlQuery<Account>(query, param)
                                     .Skip(startIndex)
                                     .Take(count)
                                     .ToList();

    foreach (Account account in accounts)
    {
        Console.WriteLine("Acc ID: {0}, Balance: {1}", account.accId, account.balance);
    }
}
```

La ventaja es que permite trabajar a más bajo nivel que Linq y está disponible para todos los lenguajes .NET.