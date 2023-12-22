[[Tema 10-Virtualización de servidores]]

Las piezas de almacenamiento suelen ser siempre el problema de rendimiento. 

El disco de cada máquina genera una carpeta vmdk (en vmware). Los sistemas de virtualización de vmware no se adaptaban a los sistemas de ficheros estándar (ext4, ntfs...). Por eso diseñaron VMFS. Permite a varios nodos escribir de forma paralela en disco.