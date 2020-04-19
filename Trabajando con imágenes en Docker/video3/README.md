# Sintaxis y buenas prácticas en Dockerfile

Ahora que ya sabemos cómo crear imágenes en Docker por medio de un Dockerfile, vamos a ver un poco más a detalle la sintaxis utilizada para crear este archivo. Veremos algunas de las instrucciones más comunes al trabajar con estos archivos, así como algunas de las buenas prácticas al momento de escribirlos.

## Encadenar instrucciones RUN

* Cada comando RUN va a ejecutarse en la capa de contenido editable del contenedor, luego se hará un commit del contenedor como una nueva imagen.
* La nueva imagen es utilizada en el siguiente paso del Dockerfile. Así que cada instrucción RUN genera una nueva capa de imagen.
* Es recomendable encadenar las instrucciones RUN en el Dockerfile para reducir el número de capas que se generan.

## Ordenar argumentos multi-línea alfabéticamente 
* Esto ayudará a evadir la duplicación de paquetes y hará el listado mucho más fácil de actualizar.

## Instrucciones CMD
* Las instrucciones CMD especifican qué comando queremos que se ejecute una vez que inicie el contenedor.
* Si no indicamos una instrucción CMD en el Dockerfile, Docker utilizará el comando default definido en la imagen base.
* Las instrucciones CMD no se ejecutan al construir la imagen, solamente se ejecutan al iniciar el contenedor.
* El comando se puede especificar en formato exec (que es el preferido) o en formato Shell.

## Docker Cache
* Cada vez que Docker ejecuta una instrucción se construye una nueva capa de imagen.
* La próxima vez, si la instrucción no ha cambiado, Docker simplemente reutilizará la capa existente.

## Instrucciones COPY
* La instrucción COPY copia nuevos archivos o directorios desde el contexto del build y los agrega al filesystem del contenedor.

## Instrucciones ADD
* La instrucción ADD nos permite no solamente copiar archivos, si no también descargar archivos desde internet y agregarlos al contenedor.
* También tienen la habilidad de desempaquetar automáticamente archivos comprimidos.
* La regla es usar COPY por transparencia y a menos de que estes completamente seguro de lo que  necesitas, utiliza ADD.