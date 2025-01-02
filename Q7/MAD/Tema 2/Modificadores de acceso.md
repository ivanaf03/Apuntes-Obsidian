[[Tema 2-El lenguaje CSharp]]

## Tipos de accesibilidad
Las clases, métodos o datos pueden ser:
+ **private:** solo se puede acceder desde la misma clase o estructura.
+ **protected:** solo se puede acceder desde la misma clase o estructura o derivados.
+ **internal:** pueden acceder a él cualquier elemento del mismo ensamblado.
+ **protected internal:** pueden acceder a él cualquier elemento del mismo ensamblado o derivados.
+ **public:** pueden acceder a él cualquier elemento del mismo ensamblado o con referencias a él.

### Consideraciones
No se puede declarar cualquier modificador en cualquier contexto. El contexto determina cuál es el modificador de acceso por defecto. 

Los namespaces son públicos por defecto y no se puede cambiar. Todo lo que se defina dentro es public o internal por defecto. La accesibilidad de un miembro nunca puede ser mayor a la de su contenedor.

Los destructores no pueden tener modificadores de accesibilidad.