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

Para accedir desde fuera, y darle privilegios al usuario desde otra maquina hay que poner el siguiente comando

~~~

GRANT ALL ON bbdd.* to 'usuario'@'192.168.22.100';

~~~

Con este comando salimos de la base de datos

~~~
exit
~~~

Y comprobamos la conexion a la base de datos

~~~

mysql -u usuario -p

~~~

Y a continuacion permitiremos el acceso a un equipo a la conexion directa a la nuestra base de datos con el siguiente comando que se mostrará..

~~~

cat /etc/mysql/mysql.conf.d/mysqld.cnf | grep bind-address
bind-address        = 127.0.0.1

 #MUY IMPORTANTE Deberemos de cambiar el bind-address       = 127.0.0.1 por el

bind-address        = 0.0.0.0

~~~

Y para finalizar reiniciamos el servidor

~~~

systemctl restart mysql

~~~

Una vez descomprimidos los ficheros de la aplicacion web al directorio "/var/www/html" aplicamos los siguientes permisos que se mostraran en pantalla:


~~~

cd /var/www/html
chmod -R 775 .
chown -R root:www-data .

~~~
