# Conceptos importantes de Docker

Docker tiene una serie de conceptos que son un poco confusos al inicio; en esta lección veremos cuáles son y a qué se refieren cada uno de ellos, así que si anteriormente escuchabas hablar sobre imágenes, contenedores, registry y no sabías a qué se referían.

### Imágenes
Las imágenes son plantillas de sólo lectura que contienen todo lo necesario para hacer que ciertas funciones sean ejecutadas (Nginx, MongoDB, PHP, etc.) y se utilizan para poder crear contenedores; estas imágenes están hechas a partir del comando docker build y pueden estar conformadas por capas de otras imágenes.

### Contenedores
Son instancias de una imágen y nos ayudan a poder tener un entorno aislado para nuestras aplicaciones.

### Registry
Es el lugar en donde podemos almacenar nuestras imágenes para poder descargarlas desde otros equipos, el registry público de Docker es el Docker Hub pero podemos nosotros hospedar nuestro propio registry en caso de necesitarlo e incluso GitLab ofrece esa funcionalidad.

### Repositorio
Es una colección de diferentes imágenes con un mismo nombre, usualmente utilizado para poder tener un versionamiento de las imágenes que vamos generando con el paso del tiempo.