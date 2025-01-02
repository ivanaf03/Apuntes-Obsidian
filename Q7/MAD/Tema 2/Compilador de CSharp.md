[[Tema 2-El lenguaje CSharp]]

## Compilador
El compilador se encuentra en `C:\windows\Microsoft.NET\Framework\vn.n.nnn\csc.exe`. La sintaxis para utilizarlo es `csc [options] [file1.cs, file2.cs, ..., fileN.cs]`.

### Opciones
Algunas opciones importantes son:
+ **/out:outputFile:** permite cambiar el nombre del archivo al compilarlo.
+ **/target:winexe:** permite generar una aplicación de windows sin abrir una ventana de consola.
+ **/target:library:** permite generar una librería DDL.
+ **/reference:libraryFile:** permite agregar referencias a librerías necesarias para la compilación.
+ **/main:classFile:** permite especificar cuál es el Main principal de la aplicación.

