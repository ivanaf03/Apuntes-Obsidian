[[Tema 4-Arquitecturas centradas en la comunicación]]

# 1.Qué es la arquitectura en repositorio?
Se basa en facilitar el intercambio de información entre componentes mediante un repositorio central compartido al que todo acceden. Se da en escenarios donde hay muchos clientes que necesitan cierta información de otros. Los clientes pueden ser productores, consumidores o ambas cosas a la vez. 

Busca minimizar el número de comunicaciones. Para ello el nodo central comunica a todos los clientes. 

Problema:
+ [c] El repositorio es el único punto de fallo.

Ejemplos:
+ [>] Sistemas de Big Data
+ [>] Sistemas de gestión de stock en e-commerce.

## 1.1.Diagrama de contexto

![[contexto repositorio.png]]

## 1.2.Diagrama de contenedores

![[contenedor repositorio.png]]

# 2.Ejemplos

## 2.1.IDEs

![[repositorio IDE.png]]

## 2.2.Repositorio clínico

![[repositorio clínico.png]]

## 2.3.Alfresco

![[alfresco.png]]