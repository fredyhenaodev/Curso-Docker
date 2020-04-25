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
PSRESULT=$(docker-compose ps -q)

if [ ! =z "$PSRESULT" ]; then
    EXEC="yes"
else
    EXEC="no"
fi

if [ $# -gt 0 ]; then

    if [ -f .env ]; then
        source .env
    fi

    if [ "$1" == "start" ]; then
        $COMPOSE up -d
    elif [ "$1" == "stop" ]; then
        $COMPOSE down

    # si el argumento es "art" utilizar
    # comandos de artisan en un nuevo contenedor "php ->nombre servicio en el archivo docker-compose"
    elif [ "$1" == "art" ]; then
        shift 1
        $COMPOSE RUN --rm \
            -w /var/www/html \
            php \
            php artisan "$@"
    # ejecutar tareas de composer
    elif [ "$1" == "composer" ]; then
        shift 1
        if [ "$EXEC" == "yes" ]; then
            $COMPOSE exec \
                php \
                composer "$@"
        else
            $COMPOSE RUN --rm \
                -w /var/www/html \
                php \
                composer "$@"
        fi
    # ejecutar pruebas de phpunit
    elif [ "$1" == "test" ]; then
        shift 1
        if [ "$EXEC" == "yes" ]; then
            $COMPOSE exec \
                php \
                ./vendor/bin/phpunit "$@"
        else
            $COMPOSE RUN --rm \
                -w /var/www/html \
                php \
                ./vendor/bin/phpunit "$@"
        fi
    # si "npm" es utilizado, correr npm
    # desde nuestro contenedor nodo
    elif [ "$1" == "npm" ]; then
        shift 1
        if [ "$EXEC" == "yes" ]; then
            $COMPOSE exec \
                node \
                npm "$@"
        else
            $COMPOSE RUN --rm \
                -w /var/www/html \
                node \
                npm "$@"
        fi
    # si "gulp" es utilizado, correr gulp
    # desde nuestro contenedor nodo
    elif [ "$1" == "gulp" ]; then
        shift 1
        if [ "$EXEC" == "yes" ]; then
            $COMPOSE exec \
                node \
                ./node_modules/.bin/gulp "$@"
        else
            $COMPOSE RUN --rm \
                -w /var/www/html \
                node \
                ./node_modules/.bin/gulp "$@"
        fi
    # si "yarn" es utilizado, correr yarn
    # desde nuestro contenedor nodo
    elif [ "$1" == "yarn" ]; then
        shift 1
        if [ "$EXEC" == "yes" ]; then
            $COMPOSE exec \
                node \
                yarn "$@"
        else
            $COMPOSE RUN --rm \
                -w /var/www/html \
                node \
                yarn "$@"
        fi
    else
        $COMPOSE "$@"
    fi
else
    $COMPOSE ps
fi
```
