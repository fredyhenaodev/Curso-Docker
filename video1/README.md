# Docker

# Link del repositorio del curso
<a href="https://github.com/dimitriacosta/curso-de-docker">Repositorio curso-docker</a>

Docker es una implementación de las tecnologías de virtualización basadas en contenedores. Las tecnologías de virtualización nos permiten, a partir de software, crear una versión virtual de un recurso tecnológico, desde una pequeña terminal hasta un sistema operativo completo. Docker lleva la virtualización un paso más lejos utilizando su motor de contenedores, pero para poder comprender bien este concepto es necesario remontarnos un poco al pasado.

### La era antes de la virtualización

Anteriormente el proceso de deploy de aplicaciones era bastante complicado, ya que constaba de todo el proceso de configuración, e incluso la adquisición de equipos para poder montar todo sobre un servidor físico.

### Llegada de la virtualización

Con el tiempo nacieron los gestores de virtualización, siendo el más conocido hypervisor, esto permitía que se pudieran emular sistemas operativos completos desde una computadora física, pudiendo tener de manera nativa un sistema operativo (por ej. Windows) y ejecutando otro completamente distinto dentro de el (por ej. Linux).

A pesar de que esto resolvía muchos problemas que se tenían al desplegar las aplicaciones desde un solo servidor físico; también tenía sus limitaciones, ya que se creaba todo un sistema operativo para ciertas funciones y estas no sacaban provecho de todo lo que podían tener a disposición.

### Uso de Contenedores

Al principio, utilizar la virtualización fue una maravilla pero la magia se acabó cuando se empezaron a desplegar muchas aplicaciones dentro de máquinas virtuales en una sola estación, cada máquina virtual necesitaba de sus propios recursos y, al desplegar muchas aplicaciones, estos se agotaban haciendo que el sistema colapsara.

Afortunadamente, Solomon Hykes tuvo una idea que revolucionaría la industria de la virtualización, crear pequeñas secciones de virtualización que solamente contengan lo más esencial para hacer que las tareas que necesitemos funcionan, en vez de virtualizar todo un sistema operativo completo, esto fue denominado como contenedores.

Los contenedores nos permiten tener una capa muy abstracta de virtualización en la que solamente podemos ejecutar una sola tarea y hacerla bien, de manera aislada, segura, escalable  y portable, siendo la respuesta a las plegarias que tenían las personas de DevOps y los SysAdmins de muchas compañías.
