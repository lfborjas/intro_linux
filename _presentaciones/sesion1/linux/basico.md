!SLIDE

#Linux

!SLIDE bullets incremental small

##Conceptos básicos

* Basado en UNIX
* Creado como proyecto en los 90s
* Simple: archivos y procesos
* Muchas distribuciones, un sólo núcleo (*kernel*)
* Seguridad: el concepto de *super-usuario*
* GNU
* GNOME vs KDE

!SLIDE

#Todo está en archivos

!SLIDE bullets 

### _algunos_ directorios importantes en linux:

* `/bin/`: Aquí están los programas ejecutables
* `/etc/`: Donde se guardan las configuraciones
* `/var/`: Donde los programas guardan archivos de uso "interno"
* `/tmp/`: Carpeta temporal, se limpia al apagar el sistema
* `/home/`: Aquí guardan datos los usuarios

!SLIDE

#Introducción a la línea de comandos

!SLIDE

##Estructura de un comando

    nombre-del-comando [opciones] [archivos-de-entrada]
    nombre-del-comando --opcion-larga -o

Por ejemplo:
  
    cd /home
    ls -l /home


!SLIDE bullets

## el comando man

Muestra ayuda sobre otros comandos:

    man cd
    man ls
    man sudo

!SLIDE bullets small

##Opciones comunes de comandos

* `comando > archivo`: envía la salida del *comando* al *archivo*
* `comando < archivo`: usa el archivo como la entrada del comando
* `comando | otro-comando`: usa la salida del primer comando como entrada del otro
* `comando ; otro-comando`: ejecutar uno y luego otro
* `comando &`: ejecuta el comando en segundo plano


