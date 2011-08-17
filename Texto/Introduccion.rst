=====================
Introducción a Python
=====================

Por qué Python?
---------------

Python es un lenguaje de programación orientado a objetos que fue creado por
Guido van Rossum a principios de los años 90 y que ha tenido un gran
crecimiento en los últimos 10 años, debido principalmente a su adopción por
parte de Google.

También está siendo adoptado por gran cantidad de científicos de distintas
disciplinas (astrónomos, biólogos, físicos y científicos sociales) como una
alternativa gratuita a *Matlab* basada en software libre. En gran parte esto se
debe a que Python es muy fácil de aprender pues posee una sintaxis muy
sencilla. Además, tiene excelente documentación de soporte, librerías
científicas de primera calidad, capacidades de graficación en dos y tres
dimensiones, y un enorme repertorio de librerías libres para realizar
prácticamente cualquier tarea imaginable (creación de sitios web, interacción
con bases de datos, creación de interfaces gráficas multi-plataforma, etc,
etc).

En este curso vamos a utilizar `Python(x,y) <http://www.pythonxy.com/>`_, un
programa que no sólo permite instalar fácilmente Python, sino que también viene
con todas las librerías necesarias para llevar a cabo un buen curso de
modelación y simulación.


Arrancar Python(x,y) y Spyder
-----------------------------

Después de haber instalado *Python(x,y)* podemos observar se crea un ícono en
el escritorio para acceder a él. Al darle doble click, vemos que se abre una
ventana, en la que oprimimos el botón que aparece justo debajo de **Spyder**.

.. Colocar imagen

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

.. figure:: Imagenes/editor.png
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

.. figure:: Imagenes/consola.png
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

.. figure:: Imagenes/object_inspector.png
   :align: center

   Inspector de Objetos

|

A su lado se encuentra el **Explorador de Variables** (Variable Explorer) que
permita revisar, editar y graficar las variables de los programas que se hayan
corrido en la consola.
 
|

.. figure:: Imagenes/variable_explorer.png
   :align: center

   Explorador de Variables

|


Mi primer programa en Python
----------------------------

El primer programa que todos realizamos es el "Hola Mundo". En Python este
programa es extremadamente sencillo, pues sólo consiste en una línea::

    print "Hola, mundo!"

Para correr este programa, lo copiamos en el Editor, guardamos el archivo con
el nombre que queramos y después oprimimos selecciones **Run** del menú *Run* o
simplemente oprimimos **F5**.

La ventaja de ``print`` es que puede imprimir distintos tipos de datos, tan
sólo con separarlos con una coma. Por ejemplo, también es válido escribir::

   print "El resultado de K es", 7+8


Tipos de datos en Python
------------------------

Como la mayoría de lenguajes de programación, Python maneja varios tipos de
datos. Los más importantes son:

Números enteros y flotantes
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con los números uno puede realizar los siguientes tipos de operaciones:

    =========   =========
    Operación   Resultado
    =========   =========
    \+		Suma           
    \-         	Resta          
    \*         	Multiplicación 
    /         	División       
    =========   =========

.. warning::

   Al dividir dos números enteros, Python realiza por defecto la división
   entera de ellos, tal como lo hacen C o C++. Es decir que el resultado de,
   por ejemplo::
   
	1/2

   no es, como uno esperaría, 0.5, sino **0**.

   Para evitar esto, lo que usualmente se hace es convertir los números a
   flotantes añadiéndoles un punto al final, de la siguiente forma::

       1./2.

   Python brinda una alternativa más sencilla para poder olvidarse de si los
   números con los que estamos trabajando son enteros o flotantes. Para ello
   debe introducirse la siguiente instrucción en la **primera línea** del
   archivo en el que estemos programando::

       from __future__ import division

**Ejercicios**
    Realizar las siguientes operaciones

    * Calcular
    
      .. math::
    
         \frac{1}{20.7^2} + 3

    * Calcular

      .. math::

      	 3.5 \times \left( 2.7 + 2^4 \right)

    * Cuántos centímetros hay en 10.000 kilómetros?

    * Cuántos segundos hay en un siglo?

    * Cuál es el número más grande que puede calcularse con tres dígitos, los
      paréntesis y los operadores +, -, *, / y **? (Tomado de *Introducción a
      Mathematica* del Prof. Jurgen Tischer)

      .. note::

      	 Para interrumpir un cálculo en la consola debe oprimirse el botón
      	 **Kill**. Después de hacerlo debe oprimirse el botón **Run** para
      	 reiniciarla.






..  LocalWords:  Python print Run LocalWords warning from future import math
..  LocalWords:  division Mathematica
