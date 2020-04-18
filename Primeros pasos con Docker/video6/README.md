# Manejo de procesos en contenedores vs máquinas virtuales

Si ya tienes tiempo trabajando con entornos de desarrollo quizá te sea familiar el uso de máquinas virtuales al momento del desarrollo de tus proyectos y quizá te preguntes ¿Por qué habría de utilizar contenedores en lugar de máquinas virtuales? La ventaja reside en las características que vimos anteriormente en la introducción a las tecnologías de virtualización las cuales son el ahorro de recursos, facilidad de portabilidad, rapidez en deployments, etc. En esta lección veremos una de estas diferencias: el manejo de procesos.

* Ejecutar tareas dentro de un contenedor en ejecución

```sh
docker exec -i -t NOMBRE_CONTENEDOR bash
```
* Ver los procesos de un contenedor
```sh
docker exec NOMBRE_CONTENEDOR ps aux
```

