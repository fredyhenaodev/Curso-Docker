# Instalación de Docker en Linux

### Preparar el repositorio

<a href="https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce">Documentación oficial</a>

1. Primero, necesitamos actualizar nuestros repositorios locales con el comando:
```sh
sudo apt-get update
```

2. Después, tenemos que instalar algunos paquetes para que apt pueda trabajar sobre https, esto lo hacemos con el siguiente comando:
```sh

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

<--Styde-->
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

```

3. Después añadimos la llave GPG oficial de Docker con el comando
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. Luego agregamos el repositorio:
```sh
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

```

### Instalar Docker

Después de tener instalado el repositorio debemos actualizar nuevamente los repositorios locales, esto con la finalidad de que Docker sea visto como un paquete que se puede instalar. Para hacerlo, nuevamente:
```sh
sudo apt-get update
```

A continuación simplemente instalamos Docker con el comando
```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Para poder hacer que nuestro usuario ejecute Docker sin la necesidad de teclear sudo, debemos agregar el grupo docker a nuestro usuario, esto lo logramos con el comando:
```sh
sudo usermod -aG docker $USER
```

Después, solamente tenemos que cerrar sesión y al volver a iniciarla, ya tendremos nuestro usuario configurado para trabajar con Docker.