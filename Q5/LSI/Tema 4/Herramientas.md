[[Tema 4-Sniffing]]

### Ejemplos
+ Bettercap
+ MITMF
+ n grep
```
ngrep -d ens33 -x O
```

### Sidejacking y cookies
Consiste en el robo de cookies de autenticación mediante xss, sniffing, etc. Con esas cookies puedo desde mi navegador acceder a la plataforma como otra persona. Las cookies se utilizan para autenticación, traceado (comunicación usuario-portal servidor), perfilado... Una cookie no es más que una string codificada con la fecha, datos de accesibilidad de la cookie, el protocolo, etc. 

En HTML5 se dejan de usar tanto las cookies y se empieza a usar el webstorage.

##### Tipos de cookies
+ Supercookies
+ Cookies persistentes (se pueden implementar con el framework evercookie mediante envíos de HSTS)
+ Zombie cookies

