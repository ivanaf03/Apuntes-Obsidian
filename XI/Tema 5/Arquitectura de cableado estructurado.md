[[Tema 5-Cableado estructurado]]

## Arquitectura
Lo recomendado es hacer una topología en estrella, con un rack en cada planta y un rack central con acceso al exterior. Se divide en subsistemas:
+ **Horizontal:** desde hosts de usuario hasta un rack de planta.
+ **Vertical:** desde los racks de planta hasta el rack principal.
+ **Campus:** unión de racks principales de distintos edificios.

Un ejemplo:
```mermaid
graph TB
  subgraph Horizontal
    A((Host Usuario 1))
    B((Host Usuario 2))
    C((Host Usuario 3))
    D((Rack P1))
    E((Rack P2))
    F((Rack P3))

    A --> D
    B --> D
    C --> E
  end

  subgraph Vertical
    D --> G((Rack Principal))
    E --> G
    F --> G
  end

  subgraph Campus
    G --> H((Rack Principal Edificio 2))
    G --> I((Rack Principal Edificio 3))
  end

  subgraph Exterior
    H --> J((Enlace Exterior))
    I --> J
  end

```
