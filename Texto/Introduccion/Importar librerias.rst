.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

==================
Importar librerías
==================

.. ipython::
   :suppress:

   In [1]: from __future__ import division

Python posee un gran variedad de librerías para todo tipo de usos, desde la
creación y apertura de archivos en cualquier sistema operativo hasta la
extracción de datos en archivos de Word o Excel, pasando por el manejo y
análisis de enormes cantidades de información provenientes de la bolsa de
valores o de experimentos astronómicos, climáticos o biológicos.

La ventaja de Python sobre otros lenguajes de programación es que posee un
avanzado mecanismo para importar librerías o comandos específicos de alguna de
ellas, lo que hace muy sencillo usarlas para beneficio del programador. A
continuación veremos las distintas formas en que puede hacerse esto.

#. La primera opción, y la más sencilla, es usar el comando ``import`` seguido
   del nombre la librería, así::

     import math

   Cuando queramos usar algún comando de la librería, debemos llamarla por su
   nombre seguido de ``.``. Inmediatamente deberá aparecer una lista con las
   funciones que hace parte de la misma. así:

   .. ipython::
      :verbatim:

      In [2]: math.
      math.__class__         math.__package__       math.asin              math.e                 math.fsum              math.modf
      math.__delattr__       math.__reduce__        math.asinh             math.erf               math.gamma             math.pi
      math.__dict__          math.__reduce_ex__     math.atan              math.erfc              math.hypot             math.pow
      math.__doc__           math.__repr__          math.atan2             math.exp               math.isinf             math.radians
      math.__format__        math.__setattr__       math.atanh             math.expm1             math.isnan             math.sin
      math.__getattribute__  math.__sizeof__        math.ceil              math.fabs              math.ldexp             math.sinh
      math.__hash__          math.__str__           math.copysign          math.factorial         math.lgamma            math.sqrt
      math.__init__          math.__subclasshook__  math.cos               math.floor             math.log               math.tan
      math.__name__          math.acos              math.cosh              math.fmod              math.log10             math.tanh
      math.__new__           math.acosh             math.degrees           math.frexp             math.log1p             math.trunc

   .. note::
   
      De no aparecer esta lista, debe oprimirse ``TAB`` si se está en la
      consola o ``CTRL + Espacio`` si se está en el editor.

   Como ``math`` es la librería de funciones matemáticas básicas de Python,
   podemos utilizarla para calcular el :math:`\textrm{sen}(\pi/2)`, por
   ejemplo:

   .. ipython::
      :suppress:
      
      In [1]: import math

   .. ipython::
      
      In [1]: math.sin(math.pi/2)


#. Otra opción es sólo llamar un comando específico de una librería
   determinada. Para ello usamos la siguiente sintaxis::

     from math import sin

   En este caso sólo se carga el comando ``sin``, sin cargar el resto de la
   librería. Esto puede ser muy ventajoso cuando la librería es grande y sólo
   queremos utilizar una pequeña funcionalidad de la misma. Otra ventaja es que
   no es necesario usar el nombre de la librería antes del comando.

   .. ipython::
      :suppress:
      
      In [1]: from math import sin

   .. ipython::
      
      In [1]: sin(3.1)

   Sin embargo, si queremos utilizar ``pi``, veremos un error en la consola,
   porque no ha sido cargado:

   .. ipython::
      
      In [1]: sin(pi)

   Para no tener que escribir una línea ``from math import ...`` por cada
   símbolo que se desee importar, se puede usar la misma sintaxis de arriba con
   cada símbolo separado por una coma::

     from math import sin, pi

   Al cargar ``pi`` de ``math`` de esta forma, ya no veremos el error anterior:

   .. ipython::
      :suppress:
      
      In [1]: from math import pi

   .. ipython::
      
      In [1]: sin(pi/2)

#. Para llamar todos los comandos de una librería sin que estén precedidos por
   su nombre, se utiliza la sintaxis::

     from math import *

   Sin embargo, esta opción no es muy recomendable ya que los comandos de
   varias librerías pueden tener el mismo nombre, lo que puede resultar en
   serias confusiones.

#. La última opción es renombrar la librería al momento de importarla. Esto es
   una práctica bastante común, pues permite utilizar nombres cortos para las
   librerías, lo que hace más fácil llamarlas con el ``.``. Para ello se usa la
   siguiente sintaxis::

     import math as mt

   En lugar de ``math`` sólo usamos ``mt``, así:

   .. ipython::
      :suppress:
      
      In [1]: import math as mt

   .. ipython::
      
      In [1]: mt.sin(mt.pi/2) 


..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing return def suppress Out in elif else if range False li
..  LocalWords:  True append while for class init self split Imagenes