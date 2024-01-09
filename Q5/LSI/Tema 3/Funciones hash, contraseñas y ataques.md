[[Tema 3-Ocultación]]

## ¿Qué es una función hash?
Una función hash es una función matemática que toma una entrada (o mensaje) y produce una cadena de caracteres de longitud fija, que suele ser una cadena hexadecimal. Esta cadena resultante se conoce comúnmente como el "hash" o "resumen hash". La característica fundamental de las funciones hash es que incluso una pequeña modificación en la entrada debería producir un cambio significativo en el hash resultante.

### SALT
El SALT es un valor aleatorio que se utiliza como parte de la operación de hashing (resumen) de contraseñas almacenadas en el archivo "shadow". Garantiza que, aunque dos usuarios tengan la misma contraseña, sus valores de hash en el archivo "shadow" serán diferentes debido al SALT único. Esto dificulta la obtención de contraseñas a partir de tablas de hash precalculadas (ataques de tablas arco iris) y hace que los ataques de fuerza bruta sean más costosos y lentos, ya que el atacante debe probar todas las combinaciones posibles con el SALT correcto.

Hashcat es una herramienta de crackeo de hashes. Otras son Cain&Abel, John... Las entradas del fichero /etc/shadow son:
```
user: $función_hash$SALT: password_hasheado_salteado: otros_parámetros

# username: hashed_password: last_password_change: minimum_days: maximum_days: warning_days: inactive_days: expiration_date:

```

### Herramientas de identificación de algoritmos de hash
+ hash-identify
+ hashid py
+ findanyhash

## Password guessing
Los ataques de password guessing son ataques contra los servicios de tipos login-password probando passwords continuamente. Son muy lentos, por eso hay que crear buenos diccionarios. Suelen dejar registros en los logs del sistema. Los captchas sirven para frenar los ataques de password guessing. Otra forma es con filtros de IP, por ejemplo, limitando los intentos que puedes hacer desde determinada IP. Normalmente los sistemas tienen un número de bloqueos y las herramientas de password guessing suelen evitarlos. Una manera de hacerlo es probando en vez de 1 usuario->n passwords, n usuarios->1 password.

Se pueden hacer con Medusa:
```
medusa -M ssh -q
medusa -h 10.11.48.x -u lsi -P p.txt - ssh -f
```

### Protección
+ **Fail2ban:** herramiienta de prevención de intrusiones que detecta ataques de password guessing.
+ **OSSEC (HIPS):** es un sistema de prevención de intrusiones a nivel de host. OSSEC realiza la monitorización continua de los registros del sistema, archivos de configuración y otros aspectos del sistema operativo.

## Contraseña en el grub
```
grub-mkpasswd-pbkdf2

Escribir en /etc/grub.d/40_custom:
	set superuser=root
	password-pbkdf2 root <hash generado por el comando anterior>

update-grub
```

## Conexiones
### Krack attack
Permite atacar al tráfico en una conexión wifi. Se basa en bloquear el mensaje 4 del handshaking para hacer que el cliente reinstale la contraseña. Se hace con un MITM.

WPA3 es el último estándar de wifi. Salió para evitar estos ataques, en 2018. Cambia la forma de realizar el handshake. Utiliza un nuevo proceso de handshake llamado "Simultaneous Authentication of Equals" (SAE). También cambia la longitud clave de cifrado, cifra las tramas de gestión. Existen nuevos ataques como Dragonblood contra WPA3.

### DNS leaks
Son situaciones en las que la información relacionada con las DNS de un usuario se filtra o se revela a terceros no autorizados, a pesar de usar una red VPN o proxy para proteger su privacidad y anonimato en línea. Estas filtraciones pueden comprometer la privacidad y el anonimato del usuario, ya que los registros de DNS pueden revelar qué sitios web está visitando y, en algunos casos, incluso su ubicación geográfica.

### Probe requests
Las "probe requests" (solicitudes de sondeo) son mensajes que un dispositivo Wi-Fi envía para buscar redes inalámbricas disponibles a su alrededor. Estas solicitudes son una parte normal del proceso que un dispositivo realiza para descubrir y conectarse a redes Wi-Fi.

El ordenador emite tramas probe request con los wifis que se tienen automáticamente memorizados. Es posible esnifarlas. En wigle.net, poniendo la MAC del router, podemos sacar hasta la casa de la persona. Se pueden configurar los puntos de acceso para que no emitan beacons.

