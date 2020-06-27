# Nextcloud con Docker Nginx y SSL

Antes de continuar con la instalación es necesario desplegar el repositorio de [Docker Nginx](https://github.com/dd-ven/docker-nginx.git)

## Requisitos

1. [Docker Engine](https://docs.docker.com/engine/install/)
2. [Docker Compose](https://docs.docker.com/compose/install/)

## Instalación

1. Clonar el repositorio:`` git clone https://github.com/dd-ven/docker-nginx-nextcloud.git``
2. Acceder al directorio: ``cd docker-nginx-nextcloud``
3. Crear una copia de ``.env.sample`` como ``.env``: ``cp .env.sample .env``
4. Modicficar las variables en ``.env`` con un editor de texto: ``nano .env``

````
#Variables MYSQL

MYSQL_ROOT_PASSWORD=rootmysql
MYSQL_PASSWORD=passwordmysql
MYSQL_DATABASE=nextclouddata
MYSQL_USER=usermysql

#Variables red nextcloud para SSL

VIRTUAL_HOST=hostprueba.es
LETSENCRYPT_EMAIL=info@hostprueba.es
````

5. Desplegar con docker compose: ``docker-compose up -d``

Elegir bases de datos para la instalacion de Nextcloud en el panel de inicio. En base de datos sustituir ``localhost`` por ``db`` y cumplimentar con los datos que se han establecido en ``.env`` para las variables MYSQL
