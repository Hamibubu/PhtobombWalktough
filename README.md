# PhtobombWalktough

HTB machine

## Reconocimiento

Primero hacemos un scaneo con nmap
![[Pasted image 20221107120209.png]]
Vemos que tiene el puerto 80 abierto así que modificamos etc/hosts para agregar nuestra variable para entrar con photobomb.htb
![[Pasted image 20221107120328.png]]
Entramos a las página web y vemos un /printer que es para el login

![[Pasted image 20221107120425.png]]
Vemos el código fuente
![[Pasted image 20221107120507.png]]
Ahí encontramos la clave para hacer el login que está en un link
Entramos y vemos que podemos hacer requests para descargar imágenes, con burpsuite vemos los parámetros
