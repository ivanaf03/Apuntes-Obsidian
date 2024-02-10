[[Tema 2-Capa acceso a datos con Spring y JPA]]

## Modelado de relaciones
Se pueden modelar relaciones 1:1, 1:N o M:N. Pueden ser unidireccionales o bidireccionales. Una relación es bidireccional cuando se puede navegar de una entidad a la otra.

En una relación entre dos entidades tenemos un lado propietario y un lado inverso:
+ **Propietario:** la entidad cuya tabla tiene la foránea que mantiene la relación.
+ **Inverso:** el otro lado (solo en relaciones bidireccionales).

![[modelado de relaciones.png]]
