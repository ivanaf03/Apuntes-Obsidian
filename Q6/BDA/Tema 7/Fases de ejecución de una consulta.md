[[Tema 7-Optimización]]
$\space$
## 1.Esquema

![[consulta interior.png]]
$\space$
### 1.1.Pasos
1. Primero se transforma a álgebra relacional. Se valida que el SQL sea correcto y los permisos de acceso sean adecuados y se transforma.
2. Se hace optimización algebraica para generar la forma canónica de la consulta.
3. Se hace optimización basada en costes.
4. Se genera el código de la consulta y se obtienen los datos a partir de él.