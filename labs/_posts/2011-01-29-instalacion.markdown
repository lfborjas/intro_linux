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

##Paso uno: Montar la imagen de disco de ubuntu

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

##Paso dos: Crear una nueva máquina virtual

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




