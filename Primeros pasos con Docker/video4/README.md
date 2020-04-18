# Mapeo de puertos y logs en Docker

A partir de ahora, vamos a dar uso de nuestros contenedores en un ámbito un poco más realista y vamos a crear un contenedor usando Nginx para levantar un servidor web, pero crear el contenedor no es suficiente para hacer que podamos acceder a él vía web, para eso necesitamos habilitar los puertos que utiliza el contenedor, así que veamos cómo podemos hacer esto en el siguiente video.

* Publicar un puerto **-p 8080(mi host):80(container)**
```sh
docker run --rm --name NOMBRE -d -p 8080:80 NOMBRE_DE_LA_IMAGEN
```

* Creando un acceso con mi directorio local al directorio de docker **-v**

```sh
docker run --rm --name NOMBRE -d -p 8080:80 -v $(pwd):/usr/share/nginx/html  NOMBRE_DE_LA_IMAGEN
```

* **pwd** recibir mi ruta actual

* Ver los logs de mi contenedor

```sh
docker logs NOMBRE_CONTENEDOR
```

* Dejar abierta la terminal para ver nuevos logs

```sh
docker logs -f NOMBRE_CONTENEDOR
```