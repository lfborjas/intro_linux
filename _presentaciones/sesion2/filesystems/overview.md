!SLIDE 
# El sistema de archivos#

!SLIDE 

#"En un sistema Unix todo es un archivo; si no, es un proceso"


!SLIDE bullets

# El archivo Kernel

* Depende de la distribución
* A veces en la carpeta `/boot`
* Contiene la interfaz entre el resto del SO y el HW

!SLIDE commandline

    $ ls -l /boot/vmlinuz*
    -rw-r--r-- 1 root root 3900960 2010-05-26 22:21 /boot/vmlinuz-2.6.31-22-generic
    -rw-r--r-- 1 root root 4034976 2010-09-16 12:14 /boot/vmlinuz-2.6.32-24-generic
    -rw-r--r-- 1 root root 4036064 2010-09-17 19:23 /boot/vmlinuz-2.6.32-25-generic

!SLIDE bullets

# El "shell"

* Para comunicarse con el SO
* Tipos:
* `bash` y `sh`; `csh`, `tcsh` y `ksh`
*  Bourne SHell + Bourne Again SHell
* `echo $SHELL`
* `cat /etc/shells`
* `grep lfborjas /etc/passwd`


!SLIDE bullets

#Archivos de configuración y temporales

* `ls -l /etc | more`
* `/etc/passwd`
* `/etc/mtab`
* `/var/tmp`
* `/tmp`


!SLIDE bullets
#Particiones de un linux

* `data`: datos + partición raíz
* `swap`: memoria virtual (el doble de la física)
* `/etc/fstab`: puntos de montaje de particiones
* `df -h`: ver detalles de particiones/montajes

!SLIDE bullets

#Sistemas de archivos

* Alto nivel: se estructura como un árbol invertido
* Bajo nivel: `ext3`, `ext4`: `inodes`; `NTFS`

!SLIDE bullets

#Rutas

* La ruta de ejecución (`$PATH`)
* Rutas absolutas: comenzando desde la raíz
* Rutas relativas: comenzando desde la carpeta actual



!SLIDE bullets

#Tipos de archivos

* Directorios: listas de archivos
* Especiales: abstracciones de dispositivos (`/dev`)
* Enlaces (links): crean _atajos_ en el árbol de archivos
* Sockets/pipes: comunicación entre procesos

!SLIDE bullets

#Enlaces

* __duros__: otro nombre para el mismo archivo
* __suaves__: otro archivo que apunta a un archivo


!SLIDE bullets

#Sockets y pipes

* __pipe (o FIFO)__: archivo de paso, _atrapa_ al proceso escritor, siempre vacío
* __socket__: no atrapa al proceso escritor, pero también es para comunicar procesos


!SLIDE bullets

#Archivos de dispositivos

* De caracter ("especiales"): entra/sale un caracter a la vez (1 byte), p.e: teclado
* De bloque: entra/sale por bloques (p.e: disco duro)

!SLIDE bullets

#Dispositivos especiales

* `/dev/null`: al leer, fin de archivo; al escribir, retornar nada
* `/dev/zero`: retorna la terminación nula (`\0`)
* `/dev/*random`: caracteres (pseudo)aleatorios
* `/dev/full`: al leer, retorna el error de disco lleno

!SLIDE bullets

#Pseudo sistemas de archivos

* `/proc`: el _procfs_, muestra procesos como archivos (`ps`)
* `/sys`: todo con lo que el kernel interactúa 

!SLIDE bullets small

#Notación 

* `-` : archivo regular
* `d` : directorio
* `l` : link (enlace)
* `c` : archivo especial
* `s` : socket
* `p` : pipe
* `b` : "block device" (driver)

!SLIDE bullets smaller
##Notación de colores

* __azul__: directorios
* __blanco__: archivos regulares
* __rojo__: archivos comprimidos
* __rosado__: imágenes
* __cian__ : enlaces
* __amarillo__ : dispositivos
* __verde__ : ejecutables
* __rojo/fondo gris__: enlaces rotos

!SLIDE bullets small
##Sufijo textual

* `ls -F`
* __/__: directorio
* __*__: ejecutable
* __-> ALGO__: enlace
* __=__: socket
* __|__: pipe

!SLIDE commandline small

    $ls -lF ~/sample
    total 32
    lrwxrwxrwx 1 lfborjas lfborjas     5 2011-02-04 21:40 enlace -> stuff/
    lrwxrwxrwx 1 lfborjas lfborjas     3 2011-02-04 21:38 roto -> foo
    -rwxr-xr-x 1 lfborjas lfborjas   699 2011-02-04 21:32 selenium_test.py*
    drwxr-xr-x 2 lfborjas lfborjas  4096 2011-02-04 21:32 stuff/
    -rw-r--r-- 1 lfborjas lfborjas 17485 2011-02-04 21:32 test.png
    -rw-r--r-- 1 lfborjas lfborjas     0 2011-02-04 21:38 texto
    -rw-r--r-- 1 lfborjas lfborjas   117 2011-02-04 21:40 texto.tar.gz

!SLIDE smbullets command

* `-rw-r--r-- 1 lfborjas lfborjas     0 2011-02-04 21:38 texto`

* Tipo
* Permisos
* Enlaces ("duros")
* Dueño
* Grupo
* Tamaño (bytes)
* Fecha 
* Nombre

!SLIDE bullets

#Fechas en archivos

* `ls -l` : última modificación
* `ls -lc`: cambio de estado
* `ls -lu`: último acceso

!SLIDE bullets smaller

#Referencias

* <http://tldp.org/LDP/www.debian.org/doc/manuals/debian-reference/ch01.en.html#_unix_like_filesystem>
* <http://tldp.org/LDP/intro-linux/intro-linux.pdf>
