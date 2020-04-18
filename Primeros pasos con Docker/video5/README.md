# Capas de imágenes en Docker

Todas las imágenes en Docker están compuestas por capas, cada capa representa un cambio importante en el sistema de archivos del contenedor y estas a su vez pueden ser compartidas entre distintas imágenes. En esta lección de nuestro Curso de Docker, te explicaremos qué son y cómo funcionan las imágenes de Docker y cómo es posible crear contenedores tomando una base en común y aun así mantener los datos aislados entre ellos.

* Ver las capas de una imagen

```sh
docker history NOMBRE_DE_LA_IMAGEN
```

* capa de contenido editable (intermedio entre la imagen y el contenedor)
* Las imagenes son inmutables