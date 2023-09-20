[[Tema 2-JDBC Conectividad de bases de datos con java]]

### Correspondencia de tipos
Un dato de tipo Java se puede almacenar en una columna cuyo tipo SQL sea consistente con el tipo Java

|**Tipo de Java**|**Tipo de SQL**|
|---|---|
|boolean|BIT|
|byte|TINYINT|
|short|SMALLINT|
|int|INTEGER|
|long|BIGINT|
|float|REAL|
|double|DOUBLE|
|java.math.BigDecimal|NUMERIC|
|String|VARCHAR o LONGVARCHAR|
|byte[]|VARBINARY o LONGVARBINARY|
|java.sql.Date|DATE|
|java.sql.Time|TIME|
|java.sql.Timestamp|TIMESTAMP|

