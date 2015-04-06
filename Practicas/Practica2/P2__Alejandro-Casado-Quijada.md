#Práctica 2. Clonar la información de un sitio web

El objetivo de esta práctica es automatizar la clonación de información de un sitio web.
Disponemos de dos maquinas, Maquina-A y Maquina-B

En Maquina-B se guardará la información del directorio /var/www/ de la Maquina-A.

Para ello hay que permitir el acceso por ssh sin contraseña y programar la tarea con contrab

##Acceso ssh sin contraseña

Primero debemos utilizar, en Maquina-B:
~~~
ssh-keygen -t dsa
~~~    

Tras esto, debemos copiar la clave a la Maquina-A usando

~~~
ssh-copy-id -i .ssh/id_dsa.pub alex@Maquina-A
~~~

Con esto conseguimos conectarnos mediante ssh a la Maquina-A sin contraseña

![ssh sin contraseña](ssh "conexión ssh sin contraseña")

##Programar tareas con crontab

La tarea que queremos automatizar es la siguiente:

~~~
rsync -avz -e ssh alex@Maquina-A:/var/www/ /var/www/
~~~

Para ello editamos el archivo /etc/crontab dejándolo así:

![Fichero crontab](crontab "Fichero crontab")

