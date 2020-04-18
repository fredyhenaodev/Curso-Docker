# Crear imágenes de Docker con docker commit

A menudo nos encontramos utilizando imágenes de Docker en nuestros proyectos y como habíamos mencionado anteriormente lo más recomendable es utilizar imágenes oficiales, sin embargo, esto no siempre es factible ya que puede darse el caso de que necesitemos hacer alguna configuración específica o puede que requiramos instalar manualmente alguna pieza de software dentro de los contenedores para poder utilizarlos posteriormente. Si no hacemos que estos cambios se persistan tendremos que estar instalando y configurando en todo momento, sin embargo hay algo que podemos hacer al respecto y es crear nuestras propias imágenes de Docker.

## Maneras de construir una imágenes
* Hacer un commit de nuestros cambios en un contenedor de Docker
* Escribir un DockerFile

### Pasos para crear la imagen
1. Iniciar un contenedor desde una imagen base.
2. Instalar git en el contenedor 
3. Hacer commit de nuestros cambios en el contenedor

* Crear una imagen nueva
```sh
docker commit ID_CONTENEDOR NOMBRE_IMAGEN:TAB
```