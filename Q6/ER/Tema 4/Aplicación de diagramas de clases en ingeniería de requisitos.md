[[Tema 4-Diagramas de clases en ingeniería de requisitos]]

# 1.Ingeniería de requisitos

## 1.1.Uso del lenguaje
Podemos partir del siguiente uso de las palabras:
+ [>] *Sustantivo:* clase, entidad del entorno

# 2.Ejemplo
```mermaid
classDiagram
    class Fluwinki {
        + makalea()
    }

    class Puffon {
	    + verrevesa()
    }

	class Maresas {
	}

	class  {
	}

    class Contalacas {
    }

    Puffon -- Casting : macalea

```

//Recordar a miña idea, qie competicion teña un atributo tipo en vez de herencia