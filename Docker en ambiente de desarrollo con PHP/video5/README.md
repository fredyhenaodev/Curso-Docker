# Resumen: imágenes de Docker y uso diario

## Notas

### Crear contenedores

Los contenedores pueden ser creados con el comando **docker run**. Al momento de ejecutar este comando podemos utilizar varias opciones disponibles en Docker, entre ellas:

* **-it** para iniciar un contenedor de manera interactiva.
* **--name** para especificar un nombre para el contenedor.
* **--rm** para eliminar el contenedor una vez que se deje de utilizar.
* **-d** para iniciar el contenedor en el background.
* **-e** para indicar variables de entorno.

### Crear imágenes
Tenemos un par de opciones para crear nuestras propias imágenes de Docker:

#### Commit

Podemos iniciar un contenedor y utilizar el comando **docker commit** sobre él para crear una imagen nueva tomando como base el contenedor que creamos:

```sh
docker commit <id_de_contenedor> <nombre_de_la_imagen>
```

#### Dockerfile

Crear un Dockerfile es la manera más sencilla de crear imágenes de Docker ya que podemos hacer todo desde un simple script que se encargará de ejecutar todas las tareas necesarias para dejar nuestra imagen como la necesitemos. El siguiente ejemplo es un Dockerfile que crea una imagen con nginx:

```php
FROM ubuntu:16.04
 
RUN apt-get update \
  && apt-get install -y nginx \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
  && ln -sf /dev/stdout /var/log/nginx/access.log \
  && ln -sf /dev/stderr /var/log/nginx/error.log \
  && echo "daemon off;" >> /etc/nginx/nginx.conf
 
EXPOSE 80
CMD ["nginx"]
```

Una vez que tengamos el Dockerfile listo podemos crear la imagen con el comando **docker build**.

### Administrar imágenes y contenedores

Usualmente tenemos que revisar los contenedores que tenemos registrados, para eso contamos con el comando **docker ps** el cuál nos muestra los contenedores en ejecución. Para mostrar también los contenedores que se encuentran detenidos utilizamos **docker ps -a**.

Por otro lado, también es posible que necesitemos consultar las imágenes que tenemos actualmente, esto puede lograrse con el comando **docker images**.

Para ver el historial de una imagen utilizamos el comando **docker history**, esto nos muestra todos los pasos utilizados para crear la imagen en cuestión.

Es posible obtener información de bajo nivel sobre nuestros contenedores, imágenes, volúmenes, redes, etc. haciendo uso del comando **docker inspect**.

### Volúmenes

Existen 2 tipos de volúmenes en Docker, aquellos que sirven para compartir información entre contenedores y el host y también existen aquellos que son para hacer persistente la información utilizada. En nuestro ejemplo utilizamos un volumen para compartir información entre un contenedor de PHP y otro de Nginx, esto con el fin de que ambos puedan interpretar los scripts de PHP.

Por otro lado, vimos cómo los volúmenes utilizados en Redis y MySQL cuentan con un volumen nombrado, estos permiten almacenar información de manera persistente sin importar si el contenedor se detiene o se elimina.

**Al inspeccionar un volumen podemos ver la ruta en la que se encuentran los archivos guardados, esta ruta es accesible directamente sólo en sistemas Linux, en caso contrario se requiere verlo a través de un contenedor.**

Crear volúmenes puede lograrse con el comando **docker volume create** y posteriormente se debe indicar un nombre para dicho volumen.

### Redes

Las redes en Docker nos permiten aislar el tráfico de red entre contenedores para distintas aplicaciones, haciendo más seguro el trabajar con redes que enlazando contenedores.

Para crear una red debemos ejecutar el comando **docker network create** y posteriormente indicar el nombre para la red.

A diferencia de ejecutar un contenedor con el parámetro **--link**, podemos agregar contenedores a la red incluso si estos ya están en ejecución.