.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*- 

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

    * Cuántos milímetros hay en la distancia de la Tierra a la Luna, que es de
      380.000 kilómetros?

    * Cuántos segundos hay en un siglo?

    * Cuál es el número más grande que puede calcularse con tres dígitos, los
      paréntesis y los operadores +, -, \*, / y \**? (Tomado de *Introducción a
      Mathematica* del Prof. Jurgen Tischer)

      .. note::

      	 Para interrumpir un cálculo en la consola debe oprimirse el botón
      	 |kill_img| **Kill**. Después de hacerlo debe oprimirse el botón
      	 |run_img| **Run** para reiniciarla.

	 .. |kill_img| image:: Imagenes/kill.png
	 .. |run_img| image:: Imagenes/run_small.png

Listas
~~~~~~

Las listas son arreglos de datos. Se definen con corchetes, y pueden contener
datos de distintos tipos (números enteros y flotantes o también los tipos que
veremos más abajo). Un ejemplo de una lista en Python es:

.. ipython::

   In [1]: li = [-5, 7, 4, 9, 1, 12, 2]

La operación más importante que se hace con las listas es la extracción de sus
elementos en distintas posiciones. Es muy importante tener en cuenta que las
listas en Python siempre empiezan con el índice 0, como los arreglos de C y
C++.

.. ipython::

   In [1]: li[0]

   In [2]: li[3]

Lo bueno de las listas en Python es que si usamos un índice más grande que
*n-1*, donde *n* es el número de elementos, Python nos da un error (en lugar de
darnos basura de la memoria)

.. ipython::

   In [1]: li[20]

Las listas son objetos mutables, es decir, sus elementos pueden modificarse de
acuerdo a la siguiente sintaxis:

.. ipython::

   In [1]: li[1] = 0

   In [2]: li

El manejo de listas en Python es muy elegante gracias a varias facilidades. En
primer lugar pueden usarse índices negativos para extraer elementos del final
de la lista hacia adelante, de esta forma:

.. ipython::

   In [1]: li[-1]

   In [2]: li[-3]

Además pueden seleccionarse fácilmente subconjuntos de una lista usando lo que
se conoce como *rebanado* (o *slicing* en inglés), que consiste en usar dos
índices separados por ``:`` al momento de tomar elementos de la lista. Al
hacerlo, Python toma los elementos que van desde el primer índice hasta uno
menos del último. Miremos un par de ejemplos:

.. ipython::

   In [1]: li[1:3]

   In [2]: li[2:6]

El rebanado también funciona si se usa un sólo índice, bien sea el superior o
el inferior, siempre que vaya acompañado de los ``:``. En estos casos se
obtiene el resultado que uno esperaría, es decir, que se tome desde el índice
que uno quiera hasta el final:

.. ipython::

   In [1]: li[2:]

o que se pare en un índice menos que el que se use como último:

.. ipython::

   In [2]: li[:-3]

Finalmente, pueden usarse las operaciones aritméticas + para concatenar dos
listas, y * para repetir varias veces los elementos de una lista, así:

.. ipython::

   In [1]: [0, 4, 7] + [2, 3]

   In [2]: [0, 1] * 4

**Ejercicios**:
  * Calcular el promedio de la siguiente lista::

      li = [3, 18, 11, 4, 14, 12, 2, 19, 4, 6, 17, 7, 14, 6, 8, 17, 7, 2, 6,\
      19, 10, 10, 9, 17, 5, 15, 3, 14, 20, 12, 20, 7, 15, 2, 17, 1, 6, 17, 2,\
      1, 12, 11, 62, 14, 9, 20, 3, 19, 4, 15]

    *Sugerencia*: Usar el comando ``sum`` para obtener la suma de los elementos
    de la lista, y el comando ``len`` para obtener cuantos elementos tiene.

  * Calcular la mediana de la lista anterior. Recordar que para calcular la
    mediana hay que organizar los datos de menor a mayor y después utilizar la
    fórmula:

    .. math::

        \tilde{x}=
	\begin{cases}
   	x_{\frac{n+1}{2}}\quad, & \textrm{si n es impar}\\
   	\frac{1}{2}\left(x_{\frac{n}{2}}+x_{\frac{n}{2}+1}\right)\quad, & \textrm{si
   	n es par}
   	\end{cases}

    donde *n* es el número de elementos de la lista.

    *Sugerencia*: Usar el comando ``sorted`` para organizar los elementos de la
    lista de menor a mayor.

  * La media móvil es un concepto usado en economía para tratar de observar si
    existe una tendencia al alza o a la baja en los precios de las acciones de
    una empresa. Para ello, lo que hace es crear una serie de promedios de
    distintos subconjuntos del conjunto de datos original.

    Por ejemplo, si en siete días las acciones de una empresa tuvieron los
    siguientes precios:

      *Precios*: 11, 12, 13, 14, 15, 16, 17

    Podemos calcular la media móvil, en periodos de cinco días, de la siguiente
    forma:

      *Primera media móvil de 5 días*: (11 + 12 + 13 + 14 + 15) / 5 = 13

      *Segunda media móvil de 5 días*: (12 + 13 + 14 + 15 + 16) / 5 = 14

      *Tercera media móvil de 5 días*: (13 + 14 + 15 + 16 + 17) / 5 = 15


    Con esta descripción, encontrar las primeras 12 medias móviles, en periodos
    de 10 días, para los siguientes precios de las acciones de Intel
    registrados entre el 24 de Marzo y el 5 de Mayo de 2010::

      Intel = [22.27, 22.19, 22.08, 22.17, 22.18, 22.13, 22.23, 22.43, 22.24,\
      22.29, 22.15, 22.39, 22.38, 22.61, 23.36, 24.05, 23.75, 23.83, 23.95,\
      23.63, 23.82, 23.87, 23.65, 23.19, 23.10, 23.33, 22.68, 23.10, 22.40,\
      22.17]

   Las acciones de Intel están a la alza o a la baja en este periodo?

   *Sugerencia* Utilizar las operaciones de rebanado descritas arriba.

   

Strings o cadenas
~~~~~~~~~~~~~~~~~

En Python las cadenas son definidas como listas de caracteres, por lo que es
posible aplicarles rebanado y las demás operaciones que vimos en la sección
anterior. Una cadena se puede formar usando comillas dobles o sencillas, de la
siguiente manera:

.. ipython::
   
   In [1]: fruta = "banano"

   In [2]: dulce = 'bocadillo'

En este caso, los operadores + y * dan los siguientes resultados:

    =========     ===============   =========
    Operación     Uso	  	    Resultado
    =========     ===============   =========
    \+            cadena + cadena   Une dos cadenas
    \* 	          cadena * número   Repite una cadena tantas veces como sea el número
    =========     ===============   =========

Con las dos variables arriba definidas podemos realizar, por ejemplo, las
siguientes operaciones:

.. ipython::

   In [3]: fruta + dulce

   In [4]: fruta * 3

   In [5]: dulce[0]

   In [6]: dulce[:7]

Sin embargo, las cadenas no pueden ser modificadas, es decir, no les puede
asignar nuevos elementos como a las listas y por tanto son inmutables. Esto lo
podemos constatar a continuación:

.. ipython::

   In [3]: fruta[2] = 'z'

Las cadenas tienen varios métodos que pueden ser de gran utilidad. A ellos se
puede acceder colocando un punto después del nombre de la variable a la que se
le haya asignado una cadena. Por ejemplo, si después de ``fruta`` colocamos un
punto, veremos que aparece:
 
.. ipython::
   
   @verbatim
   In [5]: fruta.
   fruta.__add__                      fruta.__mod__                      fruta.decode                       fruta.partition
   fruta.__class__                    fruta.__mul__                      fruta.encode                       fruta.replace
   fruta.__contains__                 fruta.__ne__                       fruta.endswith                     fruta.rfind
   fruta.__delattr__                  fruta.__new__                      fruta.expandtabs                   fruta.rindex
   fruta.__doc__                      fruta.__reduce__                   fruta.find                         fruta.rjust
   fruta.__eq__                       fruta.__reduce_ex__                fruta.format                       fruta.rpartition
   fruta.__format__                   fruta.__repr__                     fruta.index                        fruta.rsplit
   fruta.__ge__                       fruta.__rmod__                     fruta.isalnum                      fruta.rstrip
   fruta.__getattribute__             fruta.__rmul__                     fruta.isalpha                      fruta.split
   fruta.__getitem__                  fruta.__setattr__                  fruta.isdigit                      fruta.splitlines
   fruta.__getnewargs__               fruta.__sizeof__                   fruta.islower                      fruta.startswith
   fruta.__getslice__                 fruta.__str__                      fruta.isspace                      fruta.strip
   fruta.__gt__                       fruta.__subclasshook__             fruta.istitle                      fruta.swapcase
   fruta.__hash__                     fruta._formatter_field_name_split  fruta.isupper                      fruta.title
   fruta.__init__                     fruta._formatter_parser            fruta.join                         fruta.translate
   fruta.__le__                       fruta.capitalize                   fruta.ljust                        fruta.upper
   fruta.__len__                      fruta.center                       fruta.lower                        fruta.zfill
   fruta.__lt__                       fruta.count                        fruta.lstrip 

.. warning::

   Los métodos que empiezan con dos guiones abajo (``__``) son métodos internos
   de la clase, es decir que no han sido diseñados para ser usados directamente
   por el programador, y por tanto no hay que tenerlos en cuenta.

Entre estos métodos, vamos a mirar que comportamiento tienen los siguientes:

* **upper**: Convierte toda la cadena en mayúsculas

  .. ipython::

     In [2]: fruta.upper()

* **count**: Cuenta cuantas veces se repite un carácter en una cadena

  .. ipython::

     In [2]: fruta.count('a')

* **replace**: Reemplaza un carácter o parte de una cadena por otro carácter o
  cadena

  .. ipython::

     In [2]: fruta.replace('a', 'o')

     In [3]: fruta.replace('ban', 'en')

* **split**: Divide una cadena según los espacios que tenga y genera una lista
  de palabras.

  .. ipython::

      In [2]: s = "Hola, mundo!"

      In [3]: s.split()

  También puede dividir una cadena por un determinado carácter para partirla en
  varias subcadenas:

  .. ipython::

     In [2]: dulce.split('d')

**Ejercicios**
  * Tomar la variable ``dulce``, hacer que se repita 50 veces, y separar las
    palabras con un espacio, de tal forma que obtengamos algo como:

    ``'bocadillo bocadillo ...'``

  * Cuántas veces se repite la palabra ``banano`` en la siguiente cadena?::

      muchas_frutas = 'bananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobananobananobananobananobananobananobananobananobananobananobanano\
      bananobanano'

    *Sugerencia*: Usar el comando ``len`` para contar los elementos de una
    lista.

  * Para la cadena anterior, separar cada palabra con dos espacios y un guión
    en la mitad y reemplazar la *b* por una *B* y la *o* por una *O*, de tal
    forma que obtengamos algo como:
    
    ``'BananO - BananO - ...'``

  * Qué produce el método ``center``?

    Experimentar con los siguientes comandos para ver que produce:

    .. ipython::
       
       @verbatim
       In [1]: dulce.center(2)

       @verbatim
       In [2]: dulce.center(10)

       @verbatim
       In [2]: dulce.center(16)

       @verbatim
       In [2]: dulce.center(30)

..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing
