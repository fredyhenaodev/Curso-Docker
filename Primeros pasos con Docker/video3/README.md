# Contenedores de Docker a profundidad

Anteriormente vimos cómo crear un contenedor haciendo uso de la imagen de Alpine, pero es probable que hayas tenido la duda de qué pasó con los archivos que generamos dentro del contenedor, en esta lección vamos a ver qué fue lo que pasó, así como otros comandos útiles que nos van a ayudar en un futuro.

Ejecutar un proceso en el background

* esto lo hacemos utilizando el parametro **-d** detach "desacoplado" nuestro contenedor se estara ejecutando en segundo plano

```sh
docker run -d NOMBRE_DE_LA_IMAGEN sleep 1000 
```
se ejecuta el comando sleep por 1000 segundo

* Listar los contenedores que tenemos en estado **up**
```sh
docker ps
```

* Listar todos los contenedores de cualquier estatus
```sh
docker ps -a
```

* Eliminar un contenedor después de su ejecución
 ```sh
docker run --rm NOMBRE_DE_LA_IMAGEN sleep 1
```
se elimina después de dormir por un segundo

* Crear un contenedor con un nombre 
```sh
docker run --name=NOMBRE NOMBRE_DE_LA_IMAGEN
```

* Inspeccionar los contenedores para ver información de bajo nivel
```sh
docker inspect ID_CONTENEDOR
```