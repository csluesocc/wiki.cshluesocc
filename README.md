Wiki de la Comunidad de Software y Hardware Libre UESOcc
=====================
Repositorio con el código fuente para la wiki de la comunidad hecha con Dokuwiki .

* Alguna plantilla para el wiki (no es indispensable) - [Descargar alguno aquí](http://www.dokuwiki.org/template)

## ¿Qué es Dokuwiki?

Dokuwiki es un excelente software para la creación de Wikis.  Ha sido desarrollado por Andreas Gohr en PHP, no requiere de una base de datos por lo que es muy cómo para administrar, especialmente las copias de datos y la migración de los sitios.

## Instalación

* Descargamos la version estable de Dokuwiki - [Descargar aquí](http://download.dokuwiki.org/)
* Descomprimimos el paquete y eliminamos su version empaquetada.
```
$ tar zxvf dokuwiki-*.tgz

$ rm dokuwiki-*.tgz
```
* Copiamos los archivos de la carpeta `dokuwiki` dentro del directorio wiki/ en el servidor Apache y removemos la carpeta vacía.
```
$ cp -rf dokuwiki/ /var/www/wiki/

$ rm -rf dokuwiki
```
* Establecemos los permisos necesarios para el funcionamiento de la wiki. [Mas info.](https://www.dokuwiki.org/install:permissions)
```
$ cd /var/www/wiki

$ sudo chmod 777 conf data data/pages data/attic data/media data/meta data/cache data/locks data/index data/tmp data/media_attic data/media_meta
```

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
