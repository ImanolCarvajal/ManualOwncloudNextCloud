# Configuracion de el Next Cloud

1. Configuracion de MySQL

Primero ponemos el comando CREATE DATABASE bbdd;

~~~
smx2a-2021@ada-102:~/clouds$ CREATE DATABASE bbdd;
~~~

Seguidamente crearemos un usuario con su respectiva contraseña o otra que la quieras poner tuya...

~~~
smx2a-2021@ada-102:~/clouds$ CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

~~~

Y para acceder desde otra maquina tendremos que crear un usuario nuevo, con este comando..

~~~
smx2a-2021@ada-102:~/clouds$ CREATE USER 'usuario'@'192.168.22.100' IDENTIFIED WITH mysql_native_password BY 'password';

~~~

Damos los privilegios a el usuario para que pueda editar y pueda entrar...

~~~
smx2a-2021@ada-102:~/clouds$ GRANT ALL ON bbdd.* to 'usuario'@'localhost';
~~~
