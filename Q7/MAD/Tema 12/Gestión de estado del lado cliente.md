[[Tema 12-Gestión de estado]]

## Cómo se gestiona el estado en el cliente?
En el cliente, el estado se puede gestionar mediante:
+ Parámetros en la URL.
+ Elementos ocultos en los formularios.
+ Cookies.

### Parámetros en la URL
Se hace mediante la `QueryString`. Son visibles y no sirve en todos los casos.

```csharp
protected void Button1_Click(object sender, EventArgs e)
{
    string userId = "123";
    string name = "John";
    Response.Redirect($"Details.aspx?userId={userId}&name={name}");
}

----------

protected void Page_Load(object sender, EventArgs e)
{
    if (!IsPostBack)
    {
        string userId = Request.QueryString["userId"];
        string name = Request.QueryString["name"];

        if (!string.IsNullOrEmpty(userId) && !string.IsNullOrEmpty(name))
        {
            Label1.Text = $"User ID: {userId}, Name: {name}";
        }
    }
}
```

### Elementos ocultos en los formularios
El ViewState almacena estado de los controles entre una petición y la siguiente. Todos los controles tienen la propiedad `EnableViewState` que permite hacer esto. 

También se pueden añadir datos al ViewState.

```csharp
ViewState["Counter"] = 1;
```

### Cookies
Son limitadas y el usuario puede bloquearlas. 

Tienen las propiedades:
+ **Domain:** servidor desde el que se descarga la cookie.
+ **Expires:** fecha de expiración.
+ **Name:** nombre.
+ **Value:** contenido.

```csharp
// Crear una cookie
HttpCookie cookie = new HttpCookie("loginName", UserProfile.LoginName);
cookie.Expires = DateTime.Now.AddDays(3);
Response.Cookies.Add(cookie);

// Leer una cookie
HttpCookie cookie = Request.Cookies["loginName"];

// Borrar una cookie
HttpCookie cookie = Request.Cookies["loginName"];
cookie.Expires = DateTime.Now.AddDays(-1);
Reponse.Cookies.Add(cookie);
```