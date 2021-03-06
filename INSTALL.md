# SISTEMA DE RECLAMOS CENTRO DE CONTACTO (FRONTEND)

## Instalación de dependencias

**GIT**

> $ sudo apt-get install git

Para verificar la instalación: $ git --version

**CURL**

> $ sudo apt-get install curl

Para verificar la instalación: $ curl --version

**NODE mediante NVM**

> $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
>
> $ source ~/.bashrc
>
> Para verificar la instalación: nvm --version
>
> $ nvm install v8.11.2
>
> $ nvm use v8.11.2

Comprobar instalación: node -v

**ANGULAR CLI**

> $ npm install -g @angular/cli@1.7

Para verificar la instalación: $ ng --version

## Clonar el repositorio

Clonar el proyecto desde GitLab

> $ git clone https://github.com/paulpsan/reclamos-frontend

Ingresar al directorio del proyecto clonado reclamos-frontend

> $ cd reclamos-frontend

## Instalación en Desarrollo

Instalar las dependencias

> $ npm install

Iniciar aplicacion del frontend

> $ ng serve

## Instalación en Produccion

Instalar las dependencias del proyecto

> $ npm install

Compilar el proyecto

> $ npm install

> $ ng build --prod

La compilación creará la carpeta dist, lista para su publicación.

\_configuracion de APACHE

```json
<VirtualHost *:80>
    ServerName contacto.ddeduclpz.gob.bo

    DocumentRoot /var/www/frontend

    <Directory /var/www/frontend>
        RewriteEngine on

        # Don't rewrite files or directories
        RewriteCond %{REQUEST_FILENAME} -f [OR]
        RewriteCond %{REQUEST_FILENAME} -d
        RewriteRule ^ - [L]

        # Rewrite everything else to index.html
        # to allow html5 state links
        RewriteRule ^ index.html [L]
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
