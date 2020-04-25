# Escribir helper para Docker Compose

Docker provee una manera eficaz de trabajar con contenedores, sin embargo, el uso de su sintaxis puede no ser muy amigable para el usuario. Es por eso que en esta lección crearemos un helper que nos permitirá ejecutar tareas de Docker Compose con un simple comando, incrementando la productividad de los desarrolladores y facilitando la ejecución de los contenedores.

* Crear un archivo para el helper
```sh
touch NAME_FILE
```

* Hacer el script ejecutable
```sh
chmod +x NAME_FILE
```

* Creando el helper
```sh
#!/usr/bin/env bash

COMPOSE="docker-compose"

if [ $# -gt 0 ]; then
    # si el argumento es "art" utilizar
    # comandos de artisan en un nuevo contenedor "php ->nombre servicio en el archivo docker-compose"
    if [ "$1" == "art" ]; then
        shift 1
        $COMPOSE RUN --rm \
            -w /var/www/html \
            php \
            php artisan "$@"
    # ejecutar tareas de composer
    elif [ "$1" == "composer" ]; then
        shift 1
        $COMPOSE RUN --rm \
            -w /var/www/html \
            php \
            composer "$@"
    # ejecutar pruebas de phpunit
    elif [ "$1" == "test" ]; then
        $COMPOSE RUN --rm \
            -w /var/www/html \
            php \
            ./vendor/bin/phpunit "$@"
    else
        $COMPOSE "$@"
    fi
else
    $COMPOSE ps
fi
```
