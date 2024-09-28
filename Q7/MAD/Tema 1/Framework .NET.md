[[Tema 1-Introducción a .NET]]

## 
1. Solo compilar y cosas así.
2. Programar con SDK
3. Móviles.

## Arquitectura
LINQ -> SQL en tiempo de compilación
ADO.NET Entity Framework -> parecido a Hibernate

## CLR
No es una máquina virtual, pero traduce de código intermedio a código nativo. Tiene un recolector de basura. Aísla las diferentes máquinas que corren una aplicación, teóricamente, para que si se cae una no se caiga toda la aplicación.

## Librerías
Los namespaces no utilizan la nomenclatura de directorios de los package de Java, a pesar de que pueden hacerse así. Utilizan jerarquías de nombres.

Se divide en base class library y framework class library.

## Enterprise library
Se toca más bien configuración que código. 

## CTS
La integración multilenguaje se basa en el CLS.

Todo es un objeto. No hay tipos primitivos. 

```C#
int i = 8;
i.toString();
```

## CLS

## Assemblies
Son los .exe o los .dll que sirven para distrución, instalación y versionado.

## Hosting y application domains
Si un AppDomain se cuelga, el resto suelen caerse en cadena, aunque la idea es que no pasara.