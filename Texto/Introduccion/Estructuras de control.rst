.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

======================
Estructuras de Control
======================

.. ipython::
   :suppress:

   In [1]: from __future__ import division

A continuación vamos a describir las estructuras de control más importantes en
Python:

El condicional (if)
-------------------

Es quizá la estructura de control más utilizada. A continuación presentamos un
sencillo ejemplo para observar como es su sintaxis en Python::

    def mayor_o_menor(x, y):
        if x < y:
            print x, "es menor que", y
        elif x > y:
            print x, "es mayor que", y
        else:
            print x, "y", y, "son iguales"

Al aplicar esta función a distintos números obtenemos:

.. ipython::
   :suppress:

   In [1]: def mayor_o_menor(x, y):
      ...:     if x < y:
      ...:         print x, "es menor que", y
      ...:     elif x > y:
      ...:         print x, "es mayor que", y
      ...:     else:
      ...:         print x, "y", y, "son iguales"
      ...:

.. ipython::
       
   In [1]: mayor_o_menor(2, 5)

   In [2]: mayor_o_menor(100, 10)

   In [3]: mayor_o_menor(1, 1)

Algunos de los operadores con los que se pueden hacer comparaciones al momento
de usar en ``if`` son:

    ========   =========
    Operador   Resultado
    ========   =========
    ==         Igualdad
    !=         No es igual        
    <          Menor que
    >          Mayor que
    <=         Menor o igual
    >=         Mayor o igual
    not        Niega una condición
    in         Se usa para verificar si un elemento está en una lista   
    ========   =========

A excepción de ``in`` y ``not``, todos los demás operadores son similares a los
usados en otros lenguajes de programación, por lo que no vamos a mirar ejemplos
de ellos. Veamos, por tanto, sólo como funcionan los primeros:

.. ipython::

   In [15]: 3 in [1, 2, 4]

   In [16]: 3 in [1, 2, 3]

   In [17]: not 2 == 5

A través de estos ejemplos también podemos notar que los valores de verdad en
Python se escriben como ``True`` y ``False`` para verdadero y falso,
respectivamente.

**Ejercicios**
  * Definir una función ``absoluto(x)`` que tome un número entero y retorne su
    valor absoluto, así:

    .. ipython::
       :suppress:

       In [1]: def absoluto(x):
          ...:     if x < 0:
          ...:         return -x
          ...:     else:
          ...:         return x
          ...:

    .. ipython::
       
       In [1]: absoluto(6)

       In [2]: absoluto(100.22)

       In [3]: absoluto(-18.7)

  * Definir una función ``es_divisible_entre_siete(x)`` que imprima si un
    número es o no es divisible entre 7. La función debe retornar resultados
    como los siguientes:

    .. ipython::
       :suppress:

       In [1]: def es_divisible_entre_siete(x):
          ...:     if x%7 == 0:
          ...:         print x, "es divisible entre 7"
          ...:     else:
          ...:         print x, "no es divisible entre 7"
          ...:

    .. ipython::
       
       In [1]: es_divisible_entre_siete(12)

       In [2]: es_divisible_entre_siete(14)

       In [3]: es_divisible_entre_siete(32)

       In [4]: es_divisible_entre_siete(21)

    *Sugerencia*: Utilizar el operador módulo (``%``) para decidir si un número
    es múltiplo de otro. Este operador retorna el resto de la división entre
    dos números. Por tanto, si un número divide exactamente a otro, retorna
    ``0``, sino retorna cualquier otro número. Veamos algunos ejemplos:

    .. ipython::
       
       In [1]: 12%4

       In [2]: 12%6

       In [3]: 12%5

       In [4]: 25%5

       In [5]: 25%6

  * Generalizar la función anterior en una función llamada
    ``es_divisible_entre_n(x, n)`` que tome dos números enteros e imprima si el
    primero es divisible entre el segundo, así: (Tomado de *Aprenda a pensar
    como un programador con Python*)

    .. ipython::
       :suppress:

       In [1]: def es_divisible_entre_n(x, n):
          ...:     if x%n == 0:
          ...:         print x, "es divisible entre", n
          ...:     else:
          ...:         print x, "no es divisible entre", n
          ...:

    .. ipython::
       
       In [1]: es_divisible_entre_n(20, 4)

       In [2]: es_divisible_entre_n(36, 5)

  * Definir una función ``agregar_nuevo(li, x)`` que reciba una lista y un
    elemento y retorne una nueva lista en la que esté añadido el elemento, pero
    sólo si éste **no** hace parte de la lista original (Tomado de
    *Introducción a Mathematica* del Prof. Jurgen Tischer).

    Por ejemplo:

    .. ipython::
       :suppress:

       In [1]: def agregar_nuevo(li, x):
          ...:     if not x in li:
          ...:         return li + [x]
          ...:     else:
          ...:         return li
          ...:

    .. ipython::
       
       In [1]: agregar_nuevo([3,9,6], 11)

       In [1]: agregar_nuevo([3,9,6], 9)

El ciclo for
------------

En Python ``for`` se utiliza para moverse o iterar entre un conjunto de
valores. Su sintaxis es más sencilla que la usada en C o C++, porque en lugar
de utilizar un contador cuyo valor va aumentando o disminuyendo durante el
ciclo, se toma una secuencia completa (una lista, una tupla, o una cadena), y
se recorren sus elementos en el orden en que aparecen en ella.

Observemos algunos ejemplos:

.. ipython::

   In [1]: for x in [3, 9, 12, 4]:
      ...:     print x
      ...:

   In [2]: prefijos = "JKLMNOPQ"

   In [3]: sufijos = "ack"

   In [4]: for letra in prefijos:
      ...:     print letra + sufijos
      ...:

   In [5]: for i in range(10):
      ...:     print i**2
      ...:

``range`` es un comando que muy a menudo se utiliza junto a los ciclos ``for``,
pues sirve para generar una lista con todos los números desde 0 hasta *n*-1,
donde *n* es el valor que recibe. También puede usarse con dos valores, uno
como límite inferior y el otro como límite superior, así:

.. ipython::

   In [1]: range(1, 20)
      
   In [2]: range(7, 25)

**Ejercicios**:
  * Construir un ciclo ``for`` que imprima todos los números pares de 1 a 100.

    *Sugerencia*: Utilizar el operador módulo (``%``) y un ``if``.

  * Definir una función ``es_primo(x)`` que tome un número ``x`` y verifique si
    es divisible entre todos los números menores a ``x``. Si lo es, entonces debe
    retornar ``False`` y si no ``True``. Por ejemplo:

    .. ipython::
       :suppress:

       In [1]: def es_divisible_entre_n(x, n):
          ...:     if x%n == 0:
          ...:         return True
          ...:     else:
          ...:         return False
          ...:

       In [2]: def es_primo(x):
          ...:     for i in range(2, x):
          ...:         if es_divisible_entre_n(x, i):
          ...:             return False
          ...:     return True
          ...:

    .. ipython::
       
       In [1]: es_primo(10)

       In [2]: es_primo(17)

       In [3]: es_primo(15)

       In [4]: es_primo(23)

    *Sugerencia*: Modificar la función ``es_divisible_entre_n`` para que
    en lugar de imprimir oraciones, retorne ``True`` o ``False``.

  * Optimizar la función anterior, respondiendo a la siguiente pregunta: ¿Es
    necesario revisar todos los números menores a ``x`` para verificar si es
    divisible entre todos ellos? ¿Hasta qué número es en realidad necesario
    revisar?

    Para ello, definir una nueva función ``es_primo_veloz(x)`` y comparar los
    tiempos de ejecución entre ella y ``es_primo`` usando el comando
    ``%timeit`` en la consola, así:

    .. ipython::
       :suppress:

       In [1]: def es_primo_veloz(x):
          ...:     k = int(x/2)
          ...:     for i in range(2, k+1):
          ...:         if es_divisible_entre_n(x, i):
          ...:             return False
          ...:     return True
          ...:

    .. ipython::

       In [1]: %timeit es_primo(600)

       In [2]: %timeit es_primo_veloz(600)

  * Definir una función ``rango_intercuartil(li)`` que calcule el rango
    intercuartil de una lista. Recordar que éste se define como:

    .. math::

       RI = Q_{3} - Q_{1}

    donde :math:`Q_{3}` es la mediana de los datos mayores a la mediana y
    :math:`Q_{1}` es la mediana de los datos menores a la mediana.

    Por ejemplo, para la siguiente lista::

      li = [48.38,  27.6 ,  32.46,  51.94,  47.43,  48.61,  34.38,  48.98,\
            48.86,  41.45,  56.55,  25.46,  27.03,  36.72,  48.03,  36.86,\
            42.58,  44.44,  56.12,  43.86,  44.42,  42.92,  41.43,  22.81,\
            36.55,  50.89,  29.93,  47.61,  63.91,  53.98,  42.64,  27.18,\
            29.93,  31.51]

    el rango intercuartil es:

    .. ipython::
       :suppress:

       In [1]: from numpy import median

       In [2]: def rango_intercuartil(li):
          ...:     m = median(li)
          ...:     li1 = []
          ...:     li2 = []
          ...:     for x in li:
          ...:         if x < m:
          ...:             li1.append(x)
          ...:         else:
          ...:             li2.append(x)
          ...:     return median(li2) - median(li1)
          ...:     

       In [3]: li = [48.38,  27.6 ,  32.46,  51.94,  47.43,  48.61,  34.38,  48.98,\
          ...:       48.86,  41.45,  56.55,  25.46,  27.03,  36.72,  48.03,  36.86,\
          ...:       42.58,  44.44,  56.12,  43.86,  44.42,  42.92,  41.43,  22.81,\
          ...:       36.55,  50.89,  29.93,  47.61,  63.91,  53.98,  42.64,  27.18,\
          ...:       29.93,  31.51]

       In [4]: %precision 2

    .. ipython::
       
       In [1]: rango_intercuartil(li)
       

    *Sugerencias*:
    
    - Definir primero una función ``mediana(li)`` que calcule la mediana de una
      lista, de la misma forma en que se hizo en el :ref:`ejercicio <mediana>`
      de la sección de :ref:`Listas <listas-label>`. La mediana de la
      lista anterior, por ejemplo, es:

      .. ipython::
         :suppress:

         In [1]: mediana = median

      .. ipython::
         
         In [1]: mediana(li)
      

    - Dividir la lista original en dos listas ``li1`` y ``li2`` que contengan
      los elementos menores y mayores a la mediana, respectivamente, y
      calcularles a éstas nuevamente la mediana para obtener :math:`Q_{3}` y
      :math:`Q_{1}`.

      Para ello, definir ``li1 = []`` y ``li2 = []`` para que empiecen siendo
      listas vacías y utilizar el método ``append`` de cada una para añadirles
      los elementos correspondientes.

  * Definir una función ``desv_est(li)`` que calcule la desviación estándar de
    una lista, usando la fórmula:

    .. math::

       s=\sqrt{\frac{\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}}{n-1}}

    donde :math:`\bar{x}` es el promedio y :math:`n` es el número total de
    datos.

    Por ejemplo, la desviación estándar de la lista del ejemplo anterior es:

    .. ipython::
       :suppress:
    
       In [1]: from numpy import mean

       In [2]: %precision

       In [2]: def desv_est(li):
          ...:     m = mean(li)
          ...:     suma = 0
          ...:     for x in li:
          ...:         suma = suma + (x-m)**2
          ...:     return (suma/(len(li)-1.))**(0.5)
          ...:

    .. ipython::

       In [3]: desv_est(li)


El ciclo while
--------------

Finalmente vamos a mirar la sintaxis del comando ``while``, que si bien no es
tan usado como los dos anteriores, es muy útil porque permite recorrer los
elementos de una lista, tupla o cadena por medio de su índice. Esto es algo que
no puede hacerse con mucha naturalidad con ``for``, que está ideado
para recorrer los elementos directamente, sin tener que preocuparse por sus
posiciones.

Además, con ``while`` no es necesario definir un límite superior para realizar
un ciclo, como si hay que hacerlo con ``for``.

Miremos un par de ejemplos:

1. En este primer ejemplo, imprimimos la lista de todos los elementos de
   ``li``, pero seleccionándolos de ``li`` por medio de su índice.

   .. ipython::

      In [1]: li = [3, 6, 9, 11]

      In [2]: i = 0

      In [3]: while i < 4:
         ...:     print li[i]
         ...:     i += 1
         ...:

   En la última línea pueden verse un ejemplo de asignación abreviada, pues en
   lugar de escribir ``i = i+1``, escribimos ``i += 1``, lo cual es similar a
   como se hace en C o C++. Otras abreviaciones que funcionan en Python son:
   ``-=``, ``*=``, ``/=``, y ``%=``.

2. En este ejemplo vamos a imprimir los 20 primeros números que son divisibles
   entre 4:

   .. ipython::

      In [1]: i = 0

      In [2]: j = 1

      In [3]: while i <= 20:
         ...:     if es_divisible_entre_n(j, 4):
         ...:         print j
         ...:         i += 1
         ...:     j += 1
         ...:
   
   En este caso vemos cómo usar dos contadores en el ciclo, uno (``i``) para
   poder detenerlo cuando se haya obtenido el veinteavo número divisible entre
   4, y otro (``j``) para movernos entre los números mayores a ``1`` y revisar
   cuáles de ellos son divisibles entre 4.

**Ejercicios**:
  * Definir una función ``cuenta_atras(n)`` que tome un número entero ``n`` e
    imprima todos los números desde ``n`` hasta ``1`` usando un ciclo
    ``while``. Además, después de imprimir ``1``, debe imprimir ``Este es el
    fin!``.

  * Dada la siguiente cadena::

      s = "jhkdaskduwqludhlasdklashdihlasdhljakhuekysbvjkasdhlasdkhlashkdedlahskdlkbasmndkm"

    Imprimir en qué posiciones se encuentra la letra ``k``.

    *R/*::
    
      2, 6, 19, 35, 39, 45, 54, 60, 68, 71, 78

  * Utilizar la función ``es_primo_veloz`` para definir una función
    ``lista_de_primos(n)`` que genere la lista de los ``n`` primeros números
    primos. Para que puedan comparar, a continuación aparece la lista de los 20
    primeros números primos:

    .. ipython::
       :suppress:

       In [1]: def lista_de_primos(n):
          ...:     li = []
          ...:     i = 2
          ...:     while len(li) < n:
          ...:         if es_primo(i):
          ...:             li.append(i)
          ...:         i += 1
          ...:     return li
          ...:

    .. ipython::
       
       In [1]: lista_de_primos(20)

    *Sugerencia*: Definir una lista vacía y utilizar su método append para
    añadirle los números primos que vayamos encontrando.

  * Usar la función :ref:`digitos <digitos>`, para encontrar el primer número
    de 4 cifras que sea divisible entre 8 y cuya primera y última cifras sean
    iguales.

    *R/*::
    
      2032

    *Sugerencia*: Definir dos contadores: uno que empiece en ``1000`` para ir
    revisando todos los números de 4 cifras, y otro para detener el ciclo
    ``while`` tan pronto se encuentre el primer número que cumpla la condición
    deseada. 



..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing return def suppress Out in elif else if range False li
..  LocalWords:  True append while for class init self split Imagenes digitos
..  LocalWords:  ref label
