# Volúmenes con Docker

Cuando trabajamos con contenedores en Docker debemos tener cuidado de cómo vamos a almacenar la información, ya que como hemos visto con anterioridad, cuando un contenedor es eliminado, toda la información dentro de ellos también es eliminada. Afortunadamente Docker nos presenta una alternativa para que la información que vayamos guardando en los contenedores esté segura y esto lo hacemos por medio de un volumen. En esta lección veremos qué son los volúmenes, cómo podemos utilizarlos y cuales son los tipos de volúmenes que existen en Docker.

* Ver los volumenes
```sh
docker volume ls
```

* Crear un Volumen
```sh
docker volume create --driver=local NOMBRE_VOLUMEN
```