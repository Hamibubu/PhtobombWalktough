# PhtobombWalktough

HTB machine

## Reconocimiento

Primero hacemos un scaneo con nmap

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/40b3c9d9-373d-401d-ac1b-b08c6132e3d7)

Vemos que tiene el puerto 80 abierto así que modificamos etc/hosts para agregar nuestra variable para entrar con photobomb.htb

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/e349dcc5-3a21-4eaf-aa87-7db31499584f)

Entramos a la página web y vemos un /printer que es para el login

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/25eb6d63-8da4-40ae-a2c5-253e4fc8a7b9)
![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/7c17301c-e114-4a82-b41c-b94174c28bcc)

Vemos el código fuente

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/dfe892a4-0336-4f04-8959-dd859d7198d2)

Ahí encontramos la clave para hacer el login que está en un link
Entramos y vemos que podemos hacer requests para descargar imágenes, con burpsuite vemos los parámetros

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/d336c575-9174-48d8-a6a4-ff27e28f5fdc)

Al modificarlos arbitrariamente vemos que el servidor es ruby
Pero calamos ahora inyectando un reverse shell y lo encodeamos con url para la inyección

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/6d21c526-917a-431a-81a7-4f0999dadc16)

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/a3d260ac-3713-4a56-b128-52f6cad5af51)

Escuchando en netcat con nc -lvp 5555

![imagen](https://github.com/Hamibubu/PhtobombWalktough/assets/108554878/e001f358-d857-481e-aa00-d1e176bddc46)

