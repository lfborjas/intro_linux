!SLIDE 
# Laboratorio 1: Manipulación de archivos#

!SLIDE bullets 
# Instrucciones #

* Este laboratorio se trabaja en parejas
* Deberá anotar (_utilizando vi_) sus resultados en un archivo llamado `~/intro_linux/lab1`
* Por cada ejercicio encontrará dos diapositivas: una con el ejercicio en sí y otra con
  preguntas y retos que deberá completar.

!SLIDE 
# Ejercicio 1

!SLIDE code 

    cd ~
    ls .
    touch archivo
    ls -l 
    touch archivo 
    ls -l 
    touch -c otro_archivo
    ls -l 


!SLIDE bullets 

* ¿Qué función tiene el comando `touch`?
* ¿Se puede aplicar a varios archivos a la vez?
* ¿Cómo aplicaría este comando a un archivo en una carpeta distinta a la actual?

!SLIDE 
# Ejercicio 2

!SLIDE code
    
    mkdir carpeta
    ls -l .
    mkdir otra/carpeta
    mkdir -p otra/carpeta
    ls -l .
    ls -l otra
    ls -l *

!SLIDE bullets 

* ¿Para qué sirve el comando `mkdir`?
* ¿Y la opción `-p` en `mkdir`?
* ¿Cómo crearía la carpeta `/tmp/hola/mundo` con un solo comando?

!SLIDE 
#Ejercicio 3

!SLIDE code
    
    echo "soy un archivo" > archivo.txt
    cat archivo.txt
    cp archivo.txt clon.txt
    ls -l .
    car clon.txt
    mkdir carpeta
    cp archivo.txt carpeta
    ls carpeta
    
!SLIDE smbullets

* ¿Para qué sirve el comando `cp`?
* ¿Qué diferencia hay entre usar `cp` con dos archivos como argumentos y una carpeta como segundo argumento?
* ¿Qué pasa si usamos una carpeta como primer argumento a `cp`?
* ¿Y si usamos dos carpetas?
* ¿En éste último caso, qué pasaría si usáramos la opción `-R`?
* Si tuviera tres archivos `.txt` y una carpeta vacía llamada `txts` ¿cómo pondría todos esos archivos en ésta 
  con un solo comando?

!SLIDE 
#Ejercicio 4

!SLIDE code small

    mkdir carpeta
    ls .
    touch carpeta/archivo
    ls carpeta
    mv carpeta folder
    ls carpeta 
    ls folder
    touch archivo1 archivo2 archivo3 archivo4
    mv archivo1 folder
    ls folder
    mv archivo[2-4] folder
    ls folder

!SLIDE bullets

* ¿Para qué sirve el comando `mv`?
* ¿Qué efecto tiene al usar una carpeta como primer argumento?
* ¿Y cuando usamos un nombre de archivo?
* ¿A cuántas y cuáles instrucciones equivaldría `mv archivo[2-4] folder` si no usáramos el patrón `nombre[rango]`?

!SLIDE
#Ejercicio 5

!SLIDE code smaller

    mkdir borrame
    touch borrame_tambien nomeborres
    ls -l
    mkdir -p tengo/hijos/y/esposa/no/me/borres
    mkdir -p hola/mundo
    rm borrame_tambien
    rm borrame
    rm -r borrame
    rm -i nomeborres
    rm -r tengo/hijos*
    rmdir tengo
    rmdir tengo/hijos
    rmdir tengo
    mkdir yo/soy/nuevo
    touch yo/soy/nuevo/archivo
    rmdir -p yo/soy/nuevo
    rm yo/soy/nuevo/archivo
    rmdir -p yo/soy/nuevo

!SLIDE smbullets

* ¿Para qué sirve el comando `rm`?
* ¿Qué precaución hay que tener al usarlo en directorios?
* ¿Qué significa la opción `-i`?
* Averigüe qué hace la opción `-f`
* ¿Qué hace el comando `rmdir`?
* ¿Para qué sirve la opción `-p`?

!SLIDE 

#Ejercicio 6

!SLIDE code small

    echo "contenido original" > archivo
    ls -li archivo
    ln archivo fichero
    ln -s archivo file
    ls -li archivo fichero file
    rm archivo
    ls -li archivo fichero file
    echo "contenido nuevo" > archivo
    ls -li archivo fichero file
    cat fichero
    car file
    mkdir carpeta
    ln carpeta folder
    ln -s carpeta folder

!SLIDE smbullets

* ¿Qué hace el comando `ln`?
* ¿Cuál es la diferencia entre un enlace creado con `-s` y uno sin él?
  (pista, vea el número de enlaces del archivo original y a los enlaces; 
  además de la representación dada por `ls`)
* ¿Qué propiedades tienen los enlaces fuertes?
* ¿Qué pasa al crear un enlace fuerte a una carpeta? ¿Por qué pasa esto?

!SLIDE 
# Ejercicio 7


!SLIDE code
    
    echo hola
    echo "hola"
    echo "esto es texto" > texto.txt
    ls -l .
    file texto.txt


!SLIDE bullets 

* ¿Para qué sirve el comando `echo`?
* ¿Y el comando `file`?
* ¿Qué efecto tiene el operador `>`?
* ¿Y el uso de comillas dobles?



!SLIDE 
# Ejercicio 8

!SLIDE code

    wget http://www.last.fm/robots.txt 
    ls .
    file robots.txt
    cat robots.txt
    tac robots.txt
    sort robots.txt
    sort robots.txt | tac
    sort robots.txt > sorted_robots.txt
    cat robots.txt sorted_robots.txt

!SLIDE bullets 
    
* ¿Para qué sirve el comando `wget`?
* ¿Y los comandos `cat` y `tac`?
* ¿Qué hace el comando `sort`?
* ¿Qué efecto tiene el operador `|`?
* ¿Qué pasa al enviar varios archivos como entrada a `cat`?
    


!SLIDE 
# Ejercicio 9

!SLIDE code small

    echo "contenido de texto" > contenido
    cat contenido
    echo "nuevo contenido!" > contenido
    cat contenido
    echo "¿y ahora?" >> contenido
    cat contenido
    echo "contenido de texto" >> contenido
    cat contenido > nuevo
    cat noexiste >> nuevo ; cat nuevo
    cat noexiste 2> nuevo; cat nuevo
    cat tampoco 2>> nuevo; cat nuevo

!SLIDE bullets 

* ¿Qué diferencia hay entre los operadores `>` y `>>` ?
* ¿Y entre los operadores `2>` y `2>>`?
* ¿Para qué sirve el operador `;`?

!SLIDE 
# Ejercicio 10

!SLIDE code smaller

    cat > mas_contenido.txt << EOF
      Este archivo
      tiene varias líneas
      de texto adentro
      Este archivo
      tiene varias líneas
    EOF
    cat mas_contenido 
    uniq mas_contenido
    cat mas_contenido ; uniq mas_contenido
    cat noexiste ; uniq mas_contenido
    cat noexiste && uniq mas_contenido
    cat noexiste || uniq mas_contenido
    

!SLIDE bullets small 

* ¿Para qué sirve la sintaxis `comando << SEPARADOR`?
* ¿Qué pasa si vuelve a ejecutar la primera instrucción con la sintaxis `comando <<- SEPARADOR`?
* ¿Para qué sirve el comando `uniq`?
* ¿Qué efecto tienen los operadores `;`, `||` (or) y `&&` (and)?
* Si quisiera guardar la salida de `uniq mas_contenido` en un archivo nuevo, ¿qué haría?

!SLIDE 
# Ejercicio 11

!SLIDE code

    cat /var/log/syslog
    more /var/log/syslog
    head /var/log/syslog
    tail /var/log/syslog
    less /var/log/syslog

!SLIDE bullets 

* ¿Qué diferencia hay entre `cat`, `more`, `head`, `tail` y `less`?
* ¿Al usar `more`, puede uno desplazarse hacia atrás?
* ¿Y con `less`?
* ¿Cómo haría para mostrar más de lo que `tail` o `head` muestran por defecto (pista, `man`)?

!SLIDE 
# Ejercicio 12


!SLIDE code small

    wget -O json.txt http://www.ietf.org/rfc/rfc4627.txt  
    cat json.txt
    less json.txt
    sort json.txt | less
    sort json.txt | uniq | tac | less
    wc json.txt
    wc -l json.txt
    uniq json.txt | wc -l

!SLIDE bullets 

* ¿Qué efecto tiene el operador `|` (pipe)?
* ¿Cómo se relacionará el operador `|` con el concepto de archivo `pipe`?
* ¿Para qué sirve el comando `wc`?
* ¿Cómo podría contar el número de archivos en un directorio mediante un comando?
* Si se le pidiera mostrar la _unión ordenada sin duplicados_ de dos archivos, cómo lo haría?

!SLIDE 
# Ejercicio 13

!SLIDE code smaller

    look world
    look human
    (look world && look human) > human_world
    less human_world
    echo "Look the world is not human" > world_human
    cat > human_world <<- DICTIONARY
    human
    world
    DICTIONARY
    cat world_human | tr [A-Z] [a-z] | \
    tr [:blank:] \\n | sort | uniq | diff -y - human_world



!SLIDE bullets
    
* ¿Para qué sirve el comando `look`?
* ¿Qué está pasando en la tercera línea? ¿Qué efecto tienen los paréntesis?
* ¿Qué está pasando en la última línea? ¿Qué utilidad tendría si el último argumento tuviera todas
  las palabras de un idioma?
* ¿Qué efecto tiene el operador `\`?
* ¿Para qué sirve el comando `tr`? 
* ¿Para qué sirve el comando `diff`?

!SLIDE
#Ejercicio 14

!SLIDE code smaller
    
    wget -O rfc.txt http://www.ietf.org/rfc/rfc4627.txt
    mkdir -p /rfcs
    touch the_rfc_of_json rfcs/another_rfc
    ls -l *rfc*
    find . -name "*rfc*"
    find . -size +10K
    locate rfc | less
    find . -name "*rfc*" -size +10K
    find . -name "*rfc*" -exec rm {} \;
    find . -name "*rfc*"
    which vi
    whereis vi
    

!SLIDE bullets

* ¿Para qué sirve el comando `find`?
* ¿Qué efecto tienen las opciones `-name`, `-size` y `-exec`?
* ¿Para qué sirve el comando `locate`?
* ¿Y los comandos `which` y `whereis`?

!SLIDE 
#Ejercicio 15

!SLIDE code small
    
    wget http://www.schemers.org/Miscellaneous/imagine.txt
    cp imagine.txt scheme.txt
    grep Schemer imagine.txt
    rgrep Schemer .
    grep -n scheme imagine.txt
    grep -i scheme imagine.txt
    grep -nvi scheme imagine.txt
    grep -i .*y.* imagine.txt

!SLIDE bullets

* ¿Para qué sirve el comando `grep`?
* ¿En qué se distingue de `rgrep`?
* ¿Qué efecto tienen las opciones `-i`, `-n` y `-v` en la salida de `grep`?
* ¿Qué hace la última línea?
