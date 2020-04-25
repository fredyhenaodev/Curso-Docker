# Introducción a Docker Compose

## ¿Por qué Docker compose?

* Automatizar la creación de imágenes, contenedores, volúmenes y redes.
* Fácil adaptación a sistemas de integración continua.

* Construir imagenes
```sh
docker-compose build -h
```

* Crear imagenes
```sh
docker-compose build
```

* Construir volumenes, contenedores, redes, etc.
```sh
docker-compose up -d
```

* Ver los contenedores del proyecto
```sh
docker-compose ps
```