# Ejecutando nuestro primer contenedor de Docker

### Comandos
* Comando para ver las imagenes 
```sh
docker images 
```

* Descargar imagen 
```sh
docker pull NOMBRE_DE_LA_IMAGEN
```

* Iniciar contenedor
```sh
docker run NOMBRE_DE_LA_IMAGEN
```

* Parar un contenedor
```sh
docker stop $(docker ps -q)
```

* Mostrar archivos y directorios de la imagen
 ```sh
docker run NOMBRE_DE_LA_IMAGEN ls /
```

* Crear un archivo
 ```sh
touch NOMBRE_DEL_ARCHIVO
```

* Obtener una terminal del contenedor 
-el parametro -i proviene de input -> leer los comandos que recibe de nuestro teclado
-el parametro -t proviene de teteye-> mostrar una terminal nativa del contenedor en nuestra pantalla
 ```sh
docker run -i -t NOMBRE_DE_LA_IMAGEN sh
```

<a href="https://hub.docker.com/">Registry público de Docker</a>


Para poder crear nuestro primer contenedor, vamos a trabajar con la imagen Alpine. Alpine, es una distribución de Linux sumamente ligera, tanto que su imagen base solamente tiene un tamaño de 5MB. Una buena práctica en Docker, es hacer que las imágenes tengan un tamaño lo más reducido posible.

Primero que nada, debemos descargar la imagen que vamos a utilizar y esto se puede hacer de dos maneras, con el comando docker pull NOMBRE_DE_LA_IMAGEN o directamente iniciando el contenedor con el comando docker run NOMBRE_DE_LA_IMAGEN, en cualquier caso, si la imagen no la tenemos localmente se descargará del Registry.

Una vez que hayamos descargado la imagen, podemos verificar que está localmente con el comando docker images, esto nos va a mostrar todas las imágenes que tengamos en nuestra computadora así como la versión de las mismas, si al momento de descargar una imagen no especificamos la versión, por defecto nos mostrará la versión latest.

Una manera de usar los contenedores es pasándole el comando que queremos que ejecute nuestro contenedor en un parámetro, sin embargo, la idea de los contenedores es que estos empiecen a trabajar por sí mismos de manera automática, sin tener que especificar manualmente qué es lo que queremos que hagan como veremos más adelante.