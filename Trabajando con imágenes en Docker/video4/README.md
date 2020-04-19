# Publicar imágenes de Docker en Docker Hub

Ahora que ya sabemos cómo crear imágenes con Docker, vamos a requerir en algunas ocasiones compartirlas con nuestro equipo de trabajo o dejarlas accesibles para que cualquiera pueda utilizarlas. Para poder lograr esto vamos a tener que almacenar nuestras imágenes en un repositorio de Docker, los cuales se almacenan en un Registry.

En esta lección vamos a ver cómo podemos utilizar el Registry público de Docker para poder almacenar nuestros repositorios de Docker.

## Subir una imagen a Docker Hub

```sh
docker tag ID_IMAGEN NOMBRE_NUEVO

docker login

docker push NOMBRE_IMAGEN 
```

## Etiqueta Latest

* Docker utilizará latest como default cuando no se haya especificado ningún tab.
* Muchos repositorios utilizan este tab para sus imágines estables más actualizadas, sin embargo esto es solo una convención y no es obligatorio.
* Las imágenes con el tab lastest no se actualizarán automáticamente cuando una versión de la iamgen sea publicada en el repositorio.
* Evitar el uso de este tab a menos que siempre tengan en mente actualizarlo.