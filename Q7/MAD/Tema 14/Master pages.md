[[Tema 14-Master pages]]

## Qué son las Master pages?
ASP.NET antes no tenía plantillas. Pa solucionarlo, se añadieron las páginas maestras, que permiten crear un diseño común que se comparte entre las diferentes Content pages. 

Definen zonas de contenido variable mediante `<asp:ContentPlaceHolder>`. Se puede añadir más de uno por página maestra. Las páginas de contenido hacen referencia a la maestra y utilizan el controlador `<asp:Content>`. 

![[master_pages.png]]

### Contenido por defecto
Los controles `ContentPlaceHolder` pueden definir un contenido por defecto. Se muestra únicamente si la página de contenidos no lo sobrescribe.

```csharp
<asp:ContentPlaceHolder ID="Main" runat="server">
  Este es el contenido por defecto, que aparecerá si no hay
  ningún control <asp:Content> que le proporcione contenido
  en una página de contenido hija.
</asp:ContentPlaceHolder>
```

## Páginas maestras anidadas
Se puede crear una página maestra que referencia a otra. Es muy útil en sitios web grandes. 

```csharp
//Padre
<%@ Master Language="C#" AutoEventWireup="true" Codebehind="ParentMaster.master.cs"
    Inherits="WebApplication1.ParentMaster" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
    <title>New Website</title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <h1>This is parent master code</h1>
            <asp:ContentPlaceHolder ID="ContentPlaceHolder_level_1" runat="server">
            </asp:ContentPlaceHolder>
        </div>
    </form>
</body>
</html>

----------

//Hija
<%@ Master Language="C#" MasterPageFile="~/ParentMaster.Master"
    AutoEventWireup="true"
    Codebehind="ChildMaster.master.cs" Inherits="WebApplication1.ChildMaster" %>
<asp:Content ID="Content1" ContentPlaceHolderID="ContentPlaceHolder_level_1" runat="server">
    <h2>This is child master code</h2>
    <asp:ContentPlaceHolder ID="ContentPlaceHolder_level_2" runat="server">
    </asp:ContentPlaceHolder>
</asp:Content>

//Content page
<%@ Page Language="C#" MasterPageFile="~/ChildMaster.Master"
    AutoEventWireup="true" Codebehind="WebForm1.aspx.cs"
    Inherits="WebApplication1.WebForm1" Title="Untitled Page" %>
<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder_level_2" runat="server">
    <p>This is content code</p>
</asp:Content>
```

### Aplicar la página maestra del sitio web
Se puede indicar cual es la página maestra principal del sitio web en el `web.config`.

```csharp
<configuration>
  <system.web>
    <pages masterPageFile="~/MasterPage.master" />
  </system.web>
</configuration>
```

Todas las páginas con controles `Content` se combinarán con esta. Todas las páginas web seguirán el diseño de la principal, incluso las que no tienen el atributo `MasterPageFile` en la directiva `<%@Page>`.

Se puede seleccionar una página web como maestra en función del navegador:

```csharp
<%@ Page Language="C#" 
    MasterPageFile="~/General.Master"
    Chrome:MasterPageFile="~/Chrome.Master"
    Opera:MasterPageFile="~/Opera.Master" 
    ... %>
```

## Propiedad Page.Master
Para acceder a los controles de una página maestra desde una página de contenido se puede usar esta propiedad. Devuelve una referencia a la página maestra. 

Permite acceder a contenido mediante:
+ Weak typing.
+ Strong typing.

### Weak typing
Se utiliza `FindControl()`. 

```csharp
//Maestra
<asp: Label ID="Title" runat="server"/>

//Contenido
((Label)Page.Master.FindControl("Title")).Text = "Orders";
```

### Strong typing
Es la forma más recomendada. Se utiliza una propiedad pública.

```csharp
//Maestra
<asp: Label ID="Title" runat="server"/>

//Maestra.cs
public String TitleText {
	get {return Title.Text;}
	set {Title.Text=value;}
}

//Contenido
Page.Master.TitleText = "Orders";
```