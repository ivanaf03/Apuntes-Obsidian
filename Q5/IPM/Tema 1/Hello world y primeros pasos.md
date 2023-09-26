[[Tema 1-Creación de interfaces]]

```
import gi

gi.require_version('Gtk', '4.0')
from gi.repository import Gtk

if __name__=='main'
	app=Gtk.Application(aplication_id=="es.udc.fic.ipm-HelloWorld")
	app.run(None)
```

```
import gi
gi.require_version('Gtk', '4.0')
from gi.repository import Gtk

def on_destroy(widget):
    Gtk.main_quit()

# Crear la ventana
window = Gtk.Window(title="Hola Mundo")
window.set_default_size(600, 400)
window.connect("destroy", on_destroy)

# Crear el primer botón
button1 = Gtk.Button(label="Botón 1")
# Conectar una función al evento "clicked" del primer botón
button1.connect("clicked", lambda x: print("Botón 1 presionado"))

# Crear el segundo botón
button2 = Gtk.Button(label="Botón 2")
# Conectar una función al evento "clicked" del segundo botón
button2.connect("clicked", lambda x: print("Botón 2 presionado"))

# Agregar los botones a la ventana
box = Gtk.Box(orientation=Gtk.Orientation.VERTICAL, spacing=6)
box.pack_start(button1, True, True, 0)
box.pack_start(button2, True, True, 0)
window.add(box)

# Configurar el foco de teclado en el segundo botón
button2.grab_focus()

# Mostrar todos los elementos de la ventana
window.show_all()

# Ejecutar el bucle principal de GTK
Gtk.main()
```

