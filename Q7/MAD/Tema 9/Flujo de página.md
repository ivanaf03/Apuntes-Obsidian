[[Tema 9-Web Forms]]

## Ejemplo de flujo
```csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="PageFlow.aspx.cs"
    Inherits="ASP_Page_Flow_Example.PageFlow" %>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>Page Flow</title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <asp:Label ID="lblInfo" runat="server" EnableViewState="false" />
            <asp:Button ID="Button1" runat="server" Text="Button" onclick="Button1_Click" />
        </div>
    </form>
</body>
</html>

----------

namespace ASP_Page_Flow_Example
{
    public partial class PageFlow : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            lblInfo.Text += "Page.Load event handled. <br />";
            if (Page.IsPostBack)
            {
                lblInfo.Text += "<b>This is not the first time you've seen this page.</b><br />";
            }
        }

        protected void Page_Init(object sender, EventArgs e)
        {
            lblInfo.Text += "Page.Init event handled.<br />";
        }

        protected void Page_PreRender(object sender, EventArgs e)
        {
            lblInfo.Text += "Page.PreRender event handled.<br />";
        }

        protected void Page_Unload(object sender, EventArgs e)
        {
            // This text never appears because the HTML is already
            // rendered for the page at this point.
            lblInfo.Text += "Page.Unload event handled.<br />";
        }

        protected void Button1_Click(object sender, EventArgs e)
        {
            lblInfo.Text += "Button1.Click event handled.<br />";
        }
    }
}
```

Con `EnableViewState="false"` la primera vez que se carga la página tenemos:

![[enable_vs_false.png]]

Ahora pulsamos el botón:

![[button_vs_false.png]]

Si se pone `EnableViewState="true"`:

![[vs_true.png]]

## Tipos de eventos
Los eventos pueden ser:
+ **De página:** se gestionan solos si la variable `AutoEventWireup="true"`, por defecto así, y se respetan los nombres predefinidos, como `Page_Load`, `Page_Init`...
+ **De controles:** es necesario indicarlos y el nombre del `.cs` debe ser el mismo que el indicado, por ejemplo, en el `onClick`.