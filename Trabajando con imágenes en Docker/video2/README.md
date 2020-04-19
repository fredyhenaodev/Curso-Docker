# Crear imágenes de Docker con Dockerfile

En la lección anterior vimos cómo podemos crear una imagen de Docker utilizando el comando **docker commit**, esto puede resultar útil en algunos casos, pero la forma más común de crear imágenes es por medio de un Dockerfile. Un Dockerfile es un archivo de texto que nos va a permitir automatizar todos los pasos de la creación de una imagen, lo cual es muy útil ya que solamente debemos escribir este archivo una vez y podemos crear la imagen tantas veces como sea necesario.

## Dockerfile y sus instrucciones 

* Un Dockerfile es un documento de texto que contiene todas las instrucciones que el usuario provee para armar la imagen.
* Cada instrucción añadirá una nueva capa a la imagen.
* Las instrucciones especifican qué hacer cuando se construya la imagen.

### Contexto de Docker build

* El comando docker build toma la ruta para el contexto del build como un argumento
* Cuando inicia el build, el cliente de Docker va a empaquetar todos los archivos que se encuentren en en contexto del build en un tarball para posteriormente transferirlo hacia el deamon de Docker.
* Por default, Docker buscará el Dockerfile en la ruta del contexto build. 

* Construir la imagen de docker basandose en el archivo Dockerfile
```sh
docker build -t NOMBRE_IMAGEN:TAB RUTA_CONTEXTO_DOCKER
```

#### Ejemplo de un Dockerfile

* Utilizamos el parametro **-y** para no confirmar la instalación

```sh
# Toma como base la imagen 
FROM NOMBRE_IMAGEN

# Nos da a conocer quien mantendrá la imagen
LABEL maintainer="NOMBRE <text@text.com>"

# Ejecutar algunas tareas
RUN apt-get update \
  && apt-get install -y locales \
  && locale-gen en_US.UTF-8


```