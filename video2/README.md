# Arquitectura Cliente / Servidor en Docker

Docker fue creado con la idea de tener una arquitectura cliente/servidor, esto significa que para poder usar Docker debemos tener instalados ambos, cliente y el servidor en nuestras computadoras.

Como lo mencionamos, nosotros no tenemos interacción directa con el servicio de Docker, sino que para ello hacemos uso de un cliente, a lo largo de este curso nos vamos a enfocar en el cliente para la línea de comandos, sin embargo existe otro cliente llamado Kitematic que funciona de manera gráfica.

El daemon de Docker es un servicio persistente que se encarga de construir, ejecutar y distribuir nuestros contenedores de Docker.

Docker fue hecho inicialmente para funcionar únicamente en sistemas Linux ya que éste hace uso de características específicas del kernel, pero con el tiempo se fue adaptando para que pudiera ser ejecutado en sistemas OS X y Windows, sólo que en estos sistemas se ejecuta por medio de una máquina virtual y el cliente de Docker se encarga de toda la comunicación entre la máquina virtual y nuestro host local.


### Material Relacionado

<a href="https://styde.net/curso-basico-de-terminal/">Curso básico de terminal</a>