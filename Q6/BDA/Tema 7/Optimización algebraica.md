[[Tema 7-Optimización]]

## Ejemplo boletín

```sql
select numfac, nifcli, nomart
from factura f, liña l, artigo a
where f.numfac=l.numfac and l.codart=a.codart
and data < '01/06/2014'
and numli=1
```

$$
\pi_{\text{numfac}, \text{nifcli}, \text{nomart}} \left( \sigma_{\text{data} < '01/06/2014' \land \text{numli} = 1} \left( \text{factura} \times \text{liña} \times \text{artigo} \right) \right)
$$
Recordar hacer optimización:


.                                                        G o2
.                                |                                                                       |
.                            G o1 X                                                        PI codart, nomart
|                                                             |                                           |
PI numfac, nifcli                                   PI numfac, codart           ARTIGO
|                                                             |
o data < '01/06/2014'                        o numli=1
|                                                             |
FACTURA                                             LIÑA