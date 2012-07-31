.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

=========
Funciones
=========

.. ipython::
   :suppress:

   In [1]: from __future__ import division

Como en cualquier otro lenguaje, en Python también es posible definir
funciones, es decir, secuencias de enunciados que reciben ciertos datos,
ejecutan algunas operaciones sobre ellos y devuelven un resultado.

Para definir una función se usa la palabra clave ``def``, y el valor que va a
retornar siempre debe ser precedido por un ``return``. La sintaxis de una
función es como se ve a continuación::

    def NOMBRE(LISTA DE ARGUMENTOS):
        ENUNCIADOS
        return VALOR

La línea que contiene el ``return`` es opcional, pues no todas las funciones
deben retornar algo. Por ejemplo, hay algunas que sólo modifican los valores de
ciertas variables, mientras que otras sólo imprimen un valor con ``print``

.. warning::

   Es muy importante tener en cuenta que los enunciados que hacen parte de la
   función deben estar **cuatro espacios** por dentro del encabezado. En otras
   palabras, todo lo que esté indentado con cuatro espacios por dentro de la
   definición, pertenece al cuerpo de la función, ya que en Python la
   indentación es lo único que define la forma en que se agrupa el código. Sólo
   cuando el nivel de indentación se retorne al punto en que se escribió el
   primer ``def`` se considera que ha terminado la definición de la función.

Un ejemplo muy sencillo de una función que toma un argumento ``x`` y retorna
este argumento elevado al cuadrado es::

   def cuadrado(x):
       return x**2

.. ipython::
   :suppress:
   
   In [3]: def cuadrado(x):
      ...:     return x**2
      ...:

Podemos comprobar que la función esta operando correctamente al pasarle varios
argumentos y ver los resultados que retorna:

.. ipython::

   In [3]: cuadrado(3)
   
   In [4]: cuadrado(5)

   In [5]: cuadrado(10)

   In [6]: cuadrado('a')

En el último caso vemos que si intentamos pasarle a la función un argumento que
no puede ser procesado, Python simplemente retorna un error.

**Ejercicios**
  * Definir una función ``potencia`` que tome dos argumentos ``x,y`` y
    devuelva

    .. math::

       x^y

  * Definir una función ``imprimir_doble`` que tome un argumento ``x`` y lo
    imprima dos veces, con un espacio entre el una palabra y la siguiente. Por
    ejemplo, al evaluarla debe retornar:

    .. ipython::
       :suppress:

       In [1]: def imprimir_doble(x):
          ...:     print x, x
          ...:

    .. ipython::
       
       In [1]: imprimir_doble(5)

       In [2]: imprimir_doble('hola')

       In [3]: imprimir_doble([3,9,4])

  * Definir una función ``distancia`` que tome dos argumentos ``x,y``, que sean
    listas de dos elementos, y calcule la distancia entre ellos usando el
    teorema de Pitágoras:

    .. math::

       \sqrt{\left(x_{1}-y_{1}\right)^{2}+\left(x_{2}-y_{2}\right)^{2}}

    Pueden comprobar que la función está haciendo su trabajo correctamente si
    retorna estos valores:

    .. ipython::
       :suppress:

       In [1]: def distancia(x,y):
          ...:     return ( (x[0]-y[0])**2 + (x[1]-y[1])**2 )**0.5
          ...:

    .. ipython::
       
       In [1]: distancia([0,0], [1,1])

       In [2]: distancia([1,5], [2,2])

  * .. _digitos:
    
    Definir una función ``digitos`` que tome un numero ``x`` y retorne los
    dígitos de que se compone como números enteros. Por ejemplo, digitos debe
    retornar:

    .. ipython::
       :suppress:

       In [1]: def digitos(x):
          ...:     cadena_de_x = str(x)
          ...:     lista_de_x = list(cadena_de_x)
          ...:     return map(int, lista_de_x)
          ...:

    .. ipython::
       
       In [1]: digitos(1234)

       In [2]: digitos(99861)

    *Sugerencia*: Utilizar los comandos de conversión entre tipos y el comando
    ``map`` para aplicar una función a todos los elementos de una lista. Por
    ejemplo, podemos usar ``map`` con ``cuadrado`` de la siguiente forma:

    .. ipython::
       
       In [1]: map(cuadrado, [2, 3, 4, 5]) 


..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing return def suppress Out in elif else if range False li
..  LocalWords:  True append while for class init self split Imagenes
