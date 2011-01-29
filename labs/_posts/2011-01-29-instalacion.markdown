---
layout: post
title: Instalación de linux en una máquina virtual 
---

#Instalación de una distribución de linux en una máquina virtual

Al final de esta práctica usted será capaz de:

1. Crear y configurar máquinas virtuales en [virtualbox](http://www.virtualbox.org/)
2. Instalar la distribución [ubuntu](http://www.ubuntu.com/) de linux en una computadora

Para ello, necesitará lo siguiente:

* Tener instalados virtualbox y [MagicDisc](http://www.magiciso.com/tutorials/miso-magicdisc-overview.htm)
* Contar con una imagen de disco (un archivo `.iso`) de ubuntu
* Una conexión a internet

Todo el software requerido *ya se encuentra instalado y listo para usarse en la computadora que se le 
ha proporcionado en el laboratorio*, de modo que debería seguir esta guía sin mayor complicación.

##Parte uno: Montar la imagen de disco de ubuntu

Para instalar un nuevo sistema operativo en una computadora regular, nosotros siempre
necesitamos un disco de instalación. La ventaja de las máquinas virtuales es que, 
como simulan una computadora, no tienen problemas en aceptar discos simulados, de modo 
que no es necesario usar discos físicos. En esta sección aprenderá cómo usar `MagicDisc`
para simular un disco compacto a partir de un archivo `.iso`.

1. Encuentre el acceso directo a `MagicDisc` y dé doble click. *No debería pasar nada visible*, 
2. En la esquina inferior derecha, encontrará el logo de MagicDisc. Si da *click derecho* en éste, 
   verá algo como lo presentado en la siguiente figura:

   ![Paso 1](/images/paso1.png)

3. Elija la opción `Virtual CD/DVD-ROM`, y en ésta, elija una unidad de disco. En la figura
   sólo se presenta una (la unidad `E:`), pero podría haber otras; puede elegir cualquiera
   pero **recuerde qué letra eligió, pues la necesitará en otro paso de la guía**
   .Cuando elija la unidad, verá algo como lo siguiente:

   ![Paso 2](/images/paso2.png)

4. En el menú `Mount...` de la unidad de disco que acaba de elegir deberá encontrar el archivo
   `ubuntu-10.04-desktop-i386.iso` que se encuentra en el `Escritorio`


Si todo sale bien, habrá montado con éxito una imagen de disco en el sistema. Eso significa que, 
gracias al programa `MagicDisc`, su computadora ahora reconoce como un disco compacto regular
(en la unidad de disco `E:`) al archivo `.iso` de ubuntu. 

Lo que hicimos, en resumen, fue meter un disco a la computadora. Pero de una manera más complicada.
Al menos nos ahorramos diez lempiras...

##Parte dos: Crear una nueva máquina virtual

En esta sección vamos a crear una computadora "cruda": tendrá todos los recursos, pero ningún
sistema operativo. Gracias a la virtualización, podemos simular una o varias computadoras diferentes
dentro de nuestra propia computadora física, sin afectar a ésta de ninguna forma.

1. Encuentre el acceso directo a `VirtualBox` y ejecute el programa.
2. Deberá ver una pantalla como la de la figura siguiente, dé click en `New`

   ![Paso 3](/images/paso3.png)

3. Entrará al asistente de creación de la máquina virtual. Lo primero
   que deberá hacer es darle un nombre a la computadora simulada y 
   qué tipo de sistema operativo va a instalar. Si le pone `ubuntu`
   como nombre, virtualbox sabrá *automáticamente* que planea instalar un linux, 
   y elegirá por usted el tipo adecuado.
   *Ojo, aquí sólo le está
   avisando a virtualbox que planea instalar un linux, pero __no está instalándolo aún__*
   Verá algo como la siguiente figura

   ![Paso 4](/images/paso4.png)

4. El siguiente paso es
   decirle cuánta *memoria* queremos que nuestra computadora simule. 
   Como esto no es físico, no tenemos que pagar por la memoria, así que dele 
   toda la memoria disponible. Verá una ventana como la de la siguiente figura

   ![Paso 5](/images/paso5.png)

5. Ahora va a encargarse del almacenamiento. Hay aquí dos pasos involucrados: crear
   un nuevo disco de arranque y decirle cuánto espacio debe ocupar. A diferencia
   del paso anterior, el almacenamiento *crea un archivo físico en la computadora 
   húesped, así que no lo haga demasiado grande*. 
   Ambos pasos se ilustran en las figuras siguientes, asegúrese de **elegir las opciones 
   sobresaltadas**
    
   ![Paso 6](/images/paso6.png)
   ![Paso 7](/images/paso7.png)
   ![Paso 8](/images/paso8.png)
       
   Si todo sale bien, después de este paso deberá ver una ventana de progreso como la siguiente:

   ![Paso 9](/images/paso9.png)



##Parte tres: configurar la máquina virtual

Antes de instalar linux, tenemos que decirle a la máquina virtual dónde estarán algunos de
sus periféricos. En concreto, nos toca conectar las unidades de CD de la máquina física a la
virtual.


1. En la pantalla principal de virtualbox, elija la máquina virtual que acaba de crear y dé
   click en `Settings`. 
2. Unidades de CD/DVD: En el menú `Settings`, elija la opción que dice `Storage`
   en este paso deberá recordar en qué unidad montó la imagen de disco de
   ubuntu en la [parte uno](#paso-uno). Debería ver algo como lo siguiente:

   ![Paso 10](/images/paso10.png)


#Parte cuatro: instalación de ubuntu-linux

¡Al fin! En este apartado aprenderá a instalar linux (la distribución "ubuntu")
en una computadora que no tiene sistema operativo (o que tiene, pero lo va a sustituir
por ubuntu-linux). Aunque lo estaremos haciendo en una máquina virtual, los pasos son
*los mismos para una instalación en una computadora física*. 


1. Inicie la máquina virtual. Para ello, vaya a la pantalla principal de virtualbox,
   elija la máquina que acabamos de crear y dé click en `Start`
2. Si conectó bien las unidades de disco de la computadora física a esta máquina virtual,
   verá una pantalla de carga de ubuntu. Después de unos segundos, verá algo como esto:

   ![Paso 12](/images/paso12.png)

3. Elija como idioma español y dé click en `Instalar ubuntu 10.04 LTS`
4. Los teclados del laboratorio tienen una distribución estadounidense en las teclas, 
   así que para que lo que el sistema operativo entiende y lo que usted ve en el teclado coincidan
   elija la distribución para `EEUU`, como en la siguiente figura:

   ![Paso 13](/images/paso13.png)

5. En el siguiente paso prepararemos el disco para que hospede al sistema operativo. 
   como en esta instalación hemos decidido *usar todo el disco de la máquina virtual para linux*, 
   sólo debemos elegir la opción `Borrar y usar el disco entero`. Esto *eliminaría cualquier
   otro sistema operativo presente*. Afortunadamente, la instalación de ubuntu lo detectaría y nos daría otra opción.
   Como se dijo antes, elija la opción que ve en la siguiente figura:

   ![Paso 14](/images/paso14.png)

6. Si todo sale bien, veremos una pantalla de progreso en la instalación, esto puede tardar hasta una hora,
   dependiendo de la capacidad de las unidades de disco y la computadora.

7. Si la instalación termina con éxito, verá una pantalla que le dice que expulse el disco de
   instalación. Como no estamos usando un disco físico, sino una imagen `.iso`, use MagicDisc para "desmontar"
   este disco, dando click derecho en el ícono del programa, eligiendo el menú `Virtual CD/DVD ROM`, luego
   la unidad donde montó el `.iso` y en ésta, la opción `Unmount`, como se ve en la figura

   ![Paso 15](/images/paso15.png)

   


