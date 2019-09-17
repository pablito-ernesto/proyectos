# proyectos

## Installation

Este proyecto se construye con:
- composer (https://getcomposer.org)
```
sudo apt-get install composer
```
- MySQL (https://phoenixnap.com/kb/how-to-install-mysql-on-ubuntu-18-04)
- PHP 7.2 (https://www.rosehosting.com/blog/how-to-install-php-7-2-on-ubuntu-16-04/)
- Apache2
- Composer
- Git
- Subversion (?)

## Usage

- Clonar repositorio
```bash
composer install
```
- Configurar Apache2 en el directorio donde se clonó (en Directory y en DocumentRoot)
```
sudo vim /etc/apache2/sites-available/wordpress.conf
<Directory /home/ubuntu/www/proyectos/>
    AllowOverride All
</Directory>
<VirtualHost *:80>
        ServerName proyectos.com.ar
        DocumentRoot /home/ubuntu/www/proyectos/
</VirtualHost>

```
- editar el hosts (agregar una linea)
```
sudo vim /etc/hosts
```
```
127.0.1.1       proyectos.com.ar
```
- crear el schema en MySQL
```
create schema proyectos;
```

- ir a proyectos.com.ar y terminar de configurar con el wizard

### Development with Docker

Dentro de la carpeta `docker` levantar containers
```bash
docker-compose up --build
```

Una vez levantado, en otra consola conectarse al contenedor web
```bash
docker exec -it dockerhost_web /bin/bash
```

Dentro del contenedor instalar dependencias del proyecto
```bash
composer install
```

En el navegador ingresar a `http://0.0.0.0:9991` y completar la instalacion ingresando 
* `wordpress` en el nombre de base de datos, usuario y cotrasena
* `mysql` en el campo host de la bd

## Contributing
To do

## License
To do
