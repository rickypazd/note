# Guía de instalación de Docker y Docker Compose en Ubuntu 22.04

## 1. Instalar Docker

**1.1. Actualizar el sistema:**

    sudo apt update
    sudo apt upgrade -y

**1.2. Instalar las dependencias:**

    sudo apt install apt-transport-https ca-certificates curl software-properties-common

**1.3. Añadir la clave GPG oficial de Docker:**

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

**1.4. Añadir el repositorio de Docker:**

    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

**1.5. Instalar Docker:**

    sudo apt update
    sudo apt install docker-ce

**1.6. Verificar la instalación de Docker:**

    sudo docker run hello-world

## 2. Instalar Docker Compose

**2.1. Descargar la versión estable actual de Docker Compose:**

*Nota:* Reemplaza `1.29.2` con la última versión, que puedes consultar en el [repositorio oficial de GitHub de Docker Compose](https://github.com/docker/compose/releases).

    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

**2.2. Hacer el binario ejecutable:**

    sudo chmod +x /usr/local/bin/docker-compose

**2.3. Verificar la instalación:**

    docker-compose --version

## 3. (Opcional) Administrar Docker como un usuario no root

**3.1. Añadir tu usuario al grupo `docker`:**

    sudo usermod -aG docker $USER

*Nota:* Deberás cerrar la sesión y volver a entrar para que este cambio surta efecto.
