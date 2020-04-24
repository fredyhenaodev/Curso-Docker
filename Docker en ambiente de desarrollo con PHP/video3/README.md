#  Redes en Docker

Docker nos permite enlazar contenedores para que puedan tener comunicación entre sí, lo cuál está bien excepto que puede resultar un tanto complicado para los usuarios usar este método cuando son muchos los contenedores que se están utilizando. Una manera más fácil y más segura es por medio de redes, ya que nos permite aislar el tráfico que se genera entre estos contenedores para que no interfiera con otras aplicaciones que pudiéramos estar utilizando. En esta lección veremos cómo podemos hacer uso de estas redes para dar un poco más de seguridad a nuestras aplicaciones con Docker.

* Crear una red
```sh
docker network create NOMBRE_RED
```

* Asignar un contenedor a una red
```sh
docker --network NOMBRE_RED
```

* Ver las redes creadas
```sh
docker network ls
```

* Ver mas detallada la red  ---- <a href="https://stedolan.github.io/jq/">jq</a> es un plugin de json en consola
```sh
docker inspect NOMBRE_RED | jq
```

* Conectarse a una red existente 
```sh
docker network connect NOMBRE_RED CONTAINER
```