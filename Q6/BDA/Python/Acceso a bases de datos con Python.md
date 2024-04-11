[[Bases de datos avanzadas]]

## 1.Introducción
Existen varias formas de acceder a SGBD relacionales con Python. Por ejemplo:
+ **Python DB-API:** es una API independiente del SGBD que trabaja a bastante bajo nivel.
+ **Integrado con herramientas:** se usan en ciencia de datos, por ejemplo Pandas.
+ **Mapeadores objeto-relaciones:** funcionan de forma similar a Hibernate de Java, por ejemplo SQLAlchemy.

### 1.1.Apartados de un programa Python que accede a BBDD
Todo programa que use Python y acceda a bases de datos contiene:
+ Importación de los adaptadores o drivers.
+ Obtención de una conexión.
+ Obtención de un cursor.
+ Uso de un cursor para lanzar consultas SQL.
+ Desconexión y liberación de recursos.

### 1.2.Ejemplo

```python
import psycopg2

#  Obtener una conexión con la base de datos
con=psycopg2.connect(host='localhost', user='testuser', password='testpass', dbname='testdb')

#  Crear un cursor
cur=con.cursor()

#  Ejecutar una consulta
cur.exxecute('select nome, datanac from persoa where id=1')
row=cur.fetchone()
print(f"Nombre:{row[0]}, fecha de nacimiento:{row[1]}")

#  Liberar recursos
cur.close()
con.close()
```

### 1.3.Defectos del ejemplo
El ejemplo necesita 