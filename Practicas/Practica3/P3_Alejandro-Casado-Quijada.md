#Práctica 3. Balanceo de carga

El objetivo de esta practica es configurar un balanceador para que reparta la carga entre los servidores.

Para ello tenemos que crear otra máquina que hará de balanceador.

Vamos a utilizar nginx y haproxy.

##nginx

### Instalación de nginx
Para instalar nginx en Ubuntu Server debemos realizar lo siguiente:

~~~
cd /tmp/
wget http://nginx.org/keys/nginx_signing.key
apt-key add /tmp/nginx_signing.key
rm -f /tmp/nginx_signing.key
~~~

Con esto añadimos la clave del repositorio de software.

Para añadir el repositorio debemos modificar el fichero /etc/apt/sources.list así:

~~~
echo "deb http://nginx.org/packages/ubuntu/ lucid nginx" >> /etc/apt/sources.list
echo "deb-src http://nginx.org/packages/ubuntu/ lucid nginx" >> /etc/apt/sources.list
~~~

Tras esto, lo instalamos:

~~~
apt-get update
apt-get install nginx
~~~

###Balanceo de carga

Para balancear la carga debemos editar el archivo `/etc/nginx/conf.d/default.conf` de la siguiente manera:

![Archivo configuración nginx](configuracion_nginx "Archivo configuración nginx")

Tras esto, reiniciamos nginx y comprobamos que funciona el balanceo usando `curl http://ip-balanceador`

En este caso estamos usando el algoritmo de balanceo de carga round-robin

![Balanceo R-R usando nginx](balanceo-nginx "Balanceo R-R usando nginx")

Para usar el algoritmo de balanceo basado en prioridades basta con editar lo siguiente:

~~~
upstream apaches {
server ip-maquina-A weight=1;
server ip-maquina-B weight=2;
}
~~~

Siendo weight la prioridad, en este caso le hemos dado mas peso a la máquina B

![Balanceo prioridad usando nginx](balanceo-nginx-prioridad "Balanceo prioridad usando nginx")


##haproxy

###Instalación de haproxy

Para instalarlo basta con usar: `sudo apt-get install haproxy joe`

###Balanceo de carga

Para usar el algoritmo de carga round-robin en haproxy editamos su fichero de configuración, `/etc/haproxy/haproxy.cfg`, de la siguiente forma:

![Archivo configuración haproxy](configuracion-haproxy "Archivo configuración haproxy")

Ahora comprobamos que funciona correctamente, de la misma forma que con nginx

![Balanceo R-R usando haproxy](balanceo-haproxy-rr "Balanceo R-R usando haproxy")

Para utilizar un algoritmo por prioridad simplemente hay que editar lo siguiente del archivo de configuración
~~~
backend servers
    server m1 ip-maquina-A:80 weight 1 maxconn 32
    server m2 ip-maquina-B:80 weight 2 maxconn 32

~~~

Al igual que en nginx, le hemos dado mayor prioridad a la máquina-B respecto a la A

![Balanceo prioridad usando haproxy](balanceo-haproxy-prioridad "Balanceo prioridad usando haproxy")








