.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*- 

===========
Instalación
===========

Windows
-------

La forma más fácil de instalar *Python* en Windows es descargando `Python(x,y)
<http://www.pythonxy.com/>`_, un programa que además instala las librerías
científicas más importantes del lenguaje. Durante el curso vamos a usar algunas
de ellas para desarrollar varias simulaciones.

Para instalar *Spyder* deben seguirse estos pasos:

#. Descargar e instalar *IPython* usando este `archivo
   <https://github.com/downloads/ipython/ipython/ipython-0.13.py2-win32.exe>`_.

#. Descargar e instalar *Spyder* usando este archivo.


MacOS X 
-------

Aunque *Python* viene pre-instalado en las últimas versiones de Mac, no cuenta
con todas las librerías necesarias para realizar computación científica. Por
ello se recomienda descargar el DMG de *Spyder*, que aparece en este `sitio web
<http://code.google.com/p/spyderlib/downloads/list>`_. y que viene con la
versión más reciente de Python y de las librerías mencionadas.

Linux
-----

Las personas que trabajen en Linux deben seguir los pasos que aparecen a
continuación, los cuales son válidos si están usando Ubuntu o cualquier otra
distribución basada en Ubuntu o Debian:

#. Ejecutar el siguiente comando en una terminal::

      sudo apt-get install python-nose

#. Descargar este `archivo
   <http://www.fperez.org/py4science/workshop_checklist.py>`_ de Python. (Para
   ello hacer click derecho sobre el enlace y elegir la opción *Guardar
   enlace/vínculo como...* )

#. Abrir una terminal en el directorio que fue descargado el archivo anterior.

#. Ejecutar el siguiente comando::

       python workshop_checklist.py

#. Después de que haya concluido de ejecutarse este archivo (puede tomar varios
   minutos), ejecutar estos comandos::

       sudo apt-get install virtualenvwrapper

       sudo apt-get install spyder

       sudo apt-get install mercurial
       
       mkvirtualenv --system-site-packages spyder

       workon spyder

       pip install ipython

       pip install hg+https://code.google.com/p/spyderlib/



Como utilizar Spyder
--------------------

Spyder_ es un Entorno de Desarrollo Integrado (o IDE por sus siglas en inglés)
que ha sido creado para hacer más sencilla y agradable la programación de
simulaciones científicas. Su diseño ha sido inspirado por *Matlab* pero se le
han añadido características especiales para facilitar el desarrollo de
programas en Python. Durante el curso vamos a utilizar Spyder para realizar
nuestras simulaciones.

.. _Spyder: http://code.google.com/p/spyderlib/

Al abrir Spyder vemos que está compuesto de cuatro paneles. En la mitad
izquierda se encuentra el **Editor**, que es el lugar en el que vamos a
escribir nuestro código. El editor además reporta errores de sintaxis y
omisiones comunes, para que puedan ser corregidas por el programador antes de
intentar correr su código.

|

.. figure:: ../Imagenes/editor.png
   :align: center

   Editor con varios archivos abiertos

|

La parte derecha está dividida en dos secciones, cada una de las cuales
contiene varios paneles organizados en pestañas. En la parte de abajo se
encuentra la **Consola** (Console), que sirve para correr el código que se haya
escrito en el editor. Su comportamiento es similar al de la terminal de
comandos de Windows (cmd.exe). Además, permite interactuar con las variables del
programa y correr directamente código de Python o porciones de código que se
encuentren en el Editor.

|

.. figure:: ../Imagenes/consola.png
   :align: center

   Consola

|

A su lado se encuentra el **Historial de Comandos** (History Log), que guarda
la historia de todos los comandos introducidos en la Consola.

Por otro lado, en la parte superior está el **Inspector de Objetos** (Object
Inspector) que se usa para obtener ayuda instantánea sobre la función o el
comando de Python que se quiera utilizar. Este panel se actualiza
automáticamente al escribir un paréntesis después del nombre de un comando, por
lo que es bastante útil.

|

.. figure:: ../Imagenes/object_inspector.png
   :align: center

   Inspector de Objetos

|

A su lado se encuentra el **Explorador de Variables** (Variable Explorer) que
permita revisar, editar y graficar las variables de los programas que se hayan
corrido en la consola.
 
|

.. figure:: ../Imagenes/variable_explorer.png
   :align: center

   Explorador de Variables

|

..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing return def suppress Out in elif else if range False li
..  LocalWords:  True append while for class init self split Imagenes Spyder
..  LocalWords:  Windows MacOS script apt get install virtualenvwrapper
