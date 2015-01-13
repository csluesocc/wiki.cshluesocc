[Wiki de la Comunidad de Software y Hardware Libre UESOcc](http://wiki.cshluesocc.org)
=====================
Repositorio con el código fuente para la wiki de la comunidad hecha con Dokuwiki .

## Prerrequisitos
* Tener instalado un servidor local (o uno [remoto](http://aprendeenlinea.udea.edu.co/lms/moodle/mod/resource/view.php?inpopup=true&id=73890))
  * [GNU/Linux](http://www.comoinstalarlinux.com/como-instalar-apache-en-debian-7/)
  * [MAC OSX](http://www.anerbarrena.com/instalar-servidor-local-xampp-mac-os-x-4667/)
  * [Windows](http://www.ticbeat.com/tecnologias/como-instalar-servidor-web-en-tu-pc/)

## ¿Qué es Dokuwiki?

Dokuwiki es un excelente software para la creación de Wikis.  Ha sido desarrollado por Andreas Gohr en PHP, no requiere de una base de datos por lo que es muy cómo para administrar, especialmente las copias de datos y la migración de los sitios.

## Instalación

* Descargamos la version estable de Dokuwiki - [Descargar aquí](http://download.dokuwiki.org/)
* Descomprimimos el paquete y eliminamos su version empaquetada.
```
$ sudo tar zxvf dokuwiki-*.tgz

$ sudo rm dokuwiki-*.tgz
```
* Copiamos los archivos de la carpeta `dokuwiki` dentro del directorio `wiki/` en el servidor Apache y removemos la carpeta vacía.
```
$ sudo cp -rf dokuwiki/ /var/www/wiki/

$ sudo rm -rf dokuwiki
```
* Establecemos los permisos necesarios para el funcionamiento de la wiki. [Mas info.](https://www.dokuwiki.org/install:permissions)
```
$ cd /var/www/wiki

$ sudo find . -type d -exec chmod -R 0755 {} \;  #Para directorios

$ sudo find . -type f -exec chmod -R 0644 {} \;  #Para archivos
```
* Cambiamos el propietario a "www" o "www-data" (Según la configuración de apache, [Más info.](http://www.socinfo.com/ubuntu/apache/permisos)
```
$ sudo chown -R www-data:www-data .
```
Todo esto para que no de problemas cuando se este configurando y para que sea accesible en la web.

## Configuración

La configuración de la wiki se realiza vía web y corresponde con los parámetros iniciales de identificación y seguridad de la wiki.
Ingresamos a: `http://localhost/wiki/install.php` y especificamos la siguiente información según sus necesidades específicas.

* Nombre de la wiki.
* Activar ACL. [Más info](https://www.dokuwiki.org/start?id=es:acl)
* Información del usuario administrador.
* Política inicial ACL:
  * **Open Wiki**: todos pueden acceder al sitio y colaborar en él.
  * **Public Wiki**: todos pueden acceder al sitio pero sólo los usuarios registrados pueden colaborar en él.
  * **Closed Wiki**: sólo los usuarios registrados pueden acceder a él.
* Licencia del contenido.

Una vez finalizada la configuración, removemos el archivo de instalación: `$ rm wiki/install.php`

## Otras configuraciones

* [Instalar plantillas](https://www.dokuwiki.org/template)
* [Instalar plugins](https://www.dokuwiki.org/plugin_installation_instructions)
* [Manual](https://www.dokuwiki.org/start?id=es:manual)
* [Sintaxis de un artículo](https://www.dokuwiki.org/start?id=es:wiki:syntax)

El contenido de este wiki excepto donde se indique lo contrario, esta bajo la siguiente licencia:
[![CC BY SA 3.0](http://es.creativecommons.org/blog/wp-content/uploads/2013/04/by-sa_petit.png)](https://creativecommons.org/licenses/by-sa/3.0/)