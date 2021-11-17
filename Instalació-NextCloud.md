# Instalación de NextCloud

1. Primero, para instalar NextCloud hay que ir a la pagina de NextCloud y seguidamente a "get NextCLoud", Server Packages y a Download Next Cloud

2. Instalación de apache2

1. Cogemos una terminal, entramos a la carpeta de clouds y ponemos los siguientes comandos:

~~~
smx2a-2021@ada-102:~$ cd clouds/
smx2a-2021@ada-102:~/clouds$
~~~

Seguidamente ponemos el comandos apt install

~~~
smx2a-2021@ada-102:~/clouds$ apt install
~~~

Y seguidamente apt update

~~~
smx2a-2021@ada-102:~/clouds$ apt update
~~~

Instalamos el apache 2 con estos comandos:

~~~
apt install -y apache2
~~~

~~~
apt install -y mysql-server
~~~

~~~
apt install php libapache2-mod-php
~~~

~~~
apt install php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl
~~~


Y reiniciamos el servidor apache2 para que nos funcione

~~~
systemctl restart apache2
~~~
