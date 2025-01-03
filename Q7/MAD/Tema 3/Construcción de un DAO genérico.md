[[Tema 3-Implementación de persistencia con ADO.NET Entity Framework]]

## Patrón DAO
Las aplicaciones necesitan persistencia de datos. Una muy mala aproximación sería que cada objeto gestionara su propia persistencia. Si se hace esto se duplicaría mucho código y, además, código dependiente del SGBD. Si se cambia el gestor, habría que cambiar el código en todas las entidades.

El patrón DAO abstrae y encapsula todos los accesos al repositorio de datos, manejando en un único lugar la conexión con la fuente de datos. Para ello, define una interfaz que proporciona acceso a las operaciones de persistente y oculta el tipo del repositorio de datos. Para cada repositorio se hace una implementación.

![[patron_DAO.png]]

### Componentes del patrón
El patrón está formado por:
+ **BusinessObject:** servicio que necesita acceder al repositorio de datos.
+ **DataAccessObject:** abstracción de los detalles de acceso al repositorio de datos.
+ **DataSource:** fuente de datos.
+ **TransferObject:** entidad intermedia entre el DAO y el negocio.

### Ventajas
Las ventajas del DAO son:
+ Proporciona transparencia.
+ Facilita la migración.
+ Reduce la complejidad del código.
+ Centraliza todo el acceso a datos.

### Inconvenientes
Los problemas del DAO son:
+ Añade una capa extra.
+ No es útil en fuentes de datos que autogestionan la persistencia.
+ Requiere jerarquía de clases.

## DAO genérico
La interfaz del DAO genérico permite definir una serie de operaciones básicas CRUD muy utilizadas en las entidades. Se puede implementar, por ejemplo, con EntityFramework.

```CSharp
public interface IGenericDao<E, PK> {
    void Create(E entity);
    
    /// <exception cref="InstanceNotFoundException"></exception>
    E Find(PK id);
    
    Boolean Exists(PK id);
    
    void Update(E entity);
    
    /// <exception cref="InstanceNotFoundException"></exception>
    void Remove(PK id);
    
    List<E> GetAllElements();
}

----------

// Ejemplo de implementación de Create
public void Create(E entity) {
	context.AddObject(GetQualifiedEntitySetName(entityClass.Name), entity);
	context.SaveChanges();
}
```

Para implementar la persistencia en la implementación se utiliza `context`, que es una propiedad obtenida mediante inyección de dependencias. Se pueden implementar operaciones más complejas con Linq o con EntitySQL. 

### DAOs en entidades
Para realizar un DAO en una entidad concreta, se implementa el DAO genérico y se definen las operaciones necesarias.

```csharp
public List<Account> FindByUserId(long userId, int startIndex, int count)
{
    DbSet<Account> accounts = Context.Set<Account>();
    
    var result = 
        (from a in accounts
         where a.usrId == userId
         orderby a.accId
         select a)
        .Skip(startIndex)
        .Take(count)
        .ToList();
        
    return result;
}
```

Otra forma es con un contexto de vida corta haciendo `using (var accounts = new MiniBankEntities())`. El problema es que hace referencia directa al nombre del contenedor y este puede variar.

