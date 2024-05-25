[[Tema 4-Diagramas de clases en ingeniería de requisitos]]
$\space$
## 1.Tipos de relaciones
Las relaciones pueden ser:
+ Asociaciones
+ Agregaciones
+ Composiciones
+ Dependencias
+ Herencias
$\space$
### 1.1.Asociación
Una asociación implica una dependencia. Se identifica como una línea continua. Por ejemplo, el sistema accede a la base de datos o el usuario accede a la aplicación.
$\space$
### 1.2.Agregación
Representa una clase formada por otras clases. Se identifica fácilmente pensando en si una clase "contiene" a otras clases. Se representa como un rombo vacío. Por ejemplo, una carpeta contiene carpetas.
$\space$
### 1.3.Composición
Es una agregación fuerte. Indica que una parte no puede existir si las partes que la componen no existen. Por ejemplo, un frontend está compuesto por componentes.
$\space$
### 1.4.Dependencia
A veces una clase depende de otra para realizar ciertas funciones. Se representa con una flecha discontinua. Por ejemplo, un backend que gestiona pagos depende de una pasarela de pagos.
$\space$
### 1.5.Herencia
Una clase puede heredar propiedades o atributos de otra. Se representa con un triángulo. Por ejemplo, un deporte puede ser fútbol, tenis, baloncesto, etc.

![[clases relaciones.png]]