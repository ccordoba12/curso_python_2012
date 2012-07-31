.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

======
Clases
======

.. ipython::
   :suppress:

   In [1]: from __future__ import division

Python es un muy buen lenguaje orientado a objetos (como Java) en el que es muy
sencillo definir y trabajar con clases. En las secciones anteriores hemos
tenido la oportunidad de utilizar los métodos de cadenas y listas para resolver
varios ejercicios, lo que indica que en su implementación ambos tipos son
clases, cosa que también cierta para los demás (aún los números son clases!).

En esta sección veremos como definir nuestras propias clases y como asociarle
sus correspondientes atributos y métodos.

Definición e inicialización
---------------------------

En general, una clase es un objeto en el que se reúnen varias funciones
(llamadas métodos) y variables (llamadas atributos) definidas por conveniencia
por el usuario para resolver un problema en particular, organizar su código o
reutilizarlo más adelante.

En Python las clases se definen con la palabra ``class`` y se inicializan
usando el método ``__init__``, que es una función cuyo primer argumento
**siempre** debe ser la palabra ``self``. Los argumentos que vengan después de
``self`` van a usarse para darle valores iniciales a los atributos de la
clase. Miremos como se hace con un ejemplo::

  class NumeroComplejo:
      def __init__(self, r, i):
          self.real = r
          self.img = i

Vamos a usar esta clase para representar números complejos, por lo que debe
tener dos atributos: una parte real y una parte imaginaria. En este caso, éstos
están dados por ``real`` e ``img``, respectivamente.

.. note::

   Es muy importante notar que para diferenciar los atributos de una clase de
   las variables locales, en Python todo atributo debe ir precedido de
   ``self.``, como en ``self.real`` y ``self.img``.

Además de ``self``, podemos ver que ``__init__`` recibe los argumentos ``r`` e
``i``, que se utilizan para inicializar los atributos mencionados.

Para crear una instancia de la clase es necesario llamarla por su nombre, con
el número de argumentos declarados en ``__init__`` (sin contar ``self``) y
asignársela a una variable, así:

.. ipython::
   :suppress:

   In [1]: class NumeroComplejo:
      ...:     def __init__(self, r, i):
      ...:         self.real = r
      ...:         self.img = i
      ...:  

.. ipython::

   In [2]: z = NumeroComplejo(1,2)

Para comprobar que la inicialización ha funcionado correctamente, podemos
inspeccionar los atributos de la clase directamente:

.. ipython::

   In [3]: z.real

   In [4]: z.img

De esta forma puede certificarse que, efectivamente, ``z`` es un número
complejo con parte real ``1`` y parte imaginaria ``2``.

Una vez definida una instancia, también es posible modificar sus atributos por
medio de asignación, así:

.. ipython::

   In [3]: z.real = 5

   In [4]: z.real

Métodos
-------

Los métodos son funciones asociadas a una clase que operan sobre sus
atributos. Por ejemplo, a la clase anterior le podemos añadir un método que
calcule el módulo de un número complejo con la fórmula:

.. math::

   \left| z \right|=\sqrt{\textrm{Re}\left(z\right)^{2}+\textrm{Im}\left(z\right)^{2}}

Para ello redefinimos ``NumeroComplejo`` para agregarle un nuevo método
``modulo``, así::

  class NumeroComplejo:
      def __init__(self, r, i):
          self.real = r
          self.img = i
      def modulo(self):
           return (self.real**2 + self.img**2)**(1/2)

.. note::

   Al igual que para ``__init__``, el primer argumento de todo método debe ser
   ``self``, para que indicar que hace parte de la clase.

.. ipython::
   :suppress:

   In [7]: class NumeroComplejo:
      ...:       def __init__(self, r, i):
      ...:           self.real = r
      ...:           self.img = i
      ...:       def modulo(self):
      ...:            return (self.real**2 + self.img**2)**(0.5)
      ...:

   In [1]: z = NumeroComplejo(1,2)

Con ello obtenemos el siguiente resultado para el módulo del número complejo
que habíamos definido arriba:

.. ipython::

   In [2]: z.modulo()

Aquí puede parecer un poco extraño que ``modulo`` se llame sin argumentos,
cuando al definirlo en la clase se le había pasado a ``self`` como primer
argumento. Esto se debe a que ``self`` no es un argumento en sí, sino que sólo
se usa para señalar que una función es un método de la clase, como ya se
mencionó.

Otra operación que puede hacerse con números complejos es obtener su
*conjugado*. El conjugado de un complejo :math:`z`, es un nuevo número complejo
que se denota :math:`\bar{z}` y se define como

.. math::

   z=a+ib \longrightarrow \bar{z}=a-ib

Para obtener el conjugado podemos entonces agregar un nuevo método a nuestra
clase, de la siguiente forma::

  class NumeroComplejo:
      def __init__(self, r, i):
          self.real = r
          self.img = i
      def modulo(self):
           return (self.real**2 + self.img**2)**(0.5)
      def conjugado(self):
           return NumeroComplejo(self.real, -self.img)

.. ipython::
   :suppress:

   In [3]: class NumeroComplejo:
      ...:       def __init__(self, r, i):
      ...:           self.real = r
      ...:           self.img = i
      ...:       def modulo(self):
      ...:            return (self.real**2 + self.img**2)**(0.5)
      ...:       def conjugado(self):
      ...:            return NumeroComplejo(self.real, -self.img)
      ...:

   In [3]: z = NumeroComplejo(1,2)

Para calcular el conjugado de ``z`` sólo debemos llamar el método:

.. ipython::

   In [4]: z1 = z.conjugado()

   In [5]: z1.real

   In [6]: z1.img

Finalmente, vamos a añadir una función que retorne el producto de dos números
complejos. Dados dos números

.. math::

   z = a + ib

   w = c + id

su producto está dado por:

.. math::

   z \times w = (ac - bd) + i(ad + bc)

Para ello podemos escribir el siguiente método, llamado ``producto``, en
nuestra clase::

  class NumeroComplejo:
      def __init__(self, r, i):
          self.real = r
          self.img = i
      def modulo(self):
           return (self.real**2 + self.img**2)**(0.5)
      def conjugado(self):
           return NumeroComplejo(self.real, -self.img)
      def producto(self, w):
           r = self.real * w.real - self.img * w.img
           i = self.real * w.img + self.img * w.real
           return NumeroComplejo(r, i)

.. ipython::
   :suppress:

   In [4]: class NumeroComplejo:
      ...:       def __init__(self, r, i):
      ...:           self.real = r
      ...:           self.img = i
      ...:       def modulo(self):
      ...:            return (self.real**2 + self.img**2)**(0.5)
      ...:       def conjugado(self):
      ...:            return NumeroComplejo(self.real, -self.img)
      ...:       def producto(self, w):
      ...:            r = self.real * w.real - self.img * w.img
      ...:            i = self.real * w.img + self.img * w.real
      ...:            return NumeroComplejo(r, i)
      ...: 

   In [44]: z = NumeroComplejo(1,2)

.. ipython::

   In [52]: w = NumeroComplejo(4,-7)

   In [53]: x = z.producto(w)

   In [54]: x.real
   
   In [55]: x.img

Para comprobar que ``producto`` está funcionando correctamente podemos usar la
siguiente fórmula, que relaciona el módulo de un número complejo con su
conjugado:

.. math::

   \left| z \right| = \sqrt{\textrm{Re} \left( z \times \bar{z} \right)}

.. ipython::

   In [48]: z2 = z.producto(z.conjugado())

   In [2]: (z2.real)**(1/2) == z.modulo()
   
**Ejercicios**
  * Definir una clase ``Vector3D`` para representar vectores en 3
    dimensiones, con las siguientes características:

    .. ipython::
       :suppress:

       In [5]: class Vector3D:
          ...:     def __init__(self, x, y, z):
          ...:         self.x = x
          ...:         self.y = y
          ...:         self.z = z
          ...:     def punto(self, w):
          ...:         return (self.x * w.x) + (self.y * w.y) + (self.z * w.z)
          ...:     def cruz(self, w):
          ...:         x = self.y * w.z - self.z * w.y
          ...:         y = -(self.x * w.z - self.z * w.x)
          ...:         z = self.x * w.y - self.y * w.x
          ...:         return Vector3D(x,y,z)
          ...:  

    1. Tres atributos: ``x``, ``y``, y ``z``, usados para guardar sus
       coordenadas.

    2. Un método llamado ``punto`` que calcule el producto punto entre dos
       vectores, mediante la fórmula:

       .. math::

          \vec{v} \cdot \vec{w} = v_{x}w_{x} + v_{y}w_{y} + v_{z}w_{z}

      Por ejemplo, para los dos vectores definidos a continuación:

      .. ipython::

         In [60]: v = Vector3D(2,0,1)

         In [62]: w = Vector3D(1,-1,3)

      Su producto punto es:

      .. ipython::

         In [64]: v.punto(w)

    3. Un método llamado ``cruz`` que calcule el producto cruz entre dos
       vectores mediante la fórmula:

       .. math::

          \vec{v} \times \vec{w} = \left(v_{y}w_{z}-v_{z}w_{y}\right)\hat{i} -
          \left(v_{x}w_{z}-v_{z}w_{x}\right)\hat{j} + \left(v_{x}w_{y}-
          v_{y}w_{x}\right)\hat{k}

       Por ejemplo, para los vectores definidos arriba el producto
       :math:`\vec{v} \times \vec{w}` es igual a:

       .. ipython::

          In [65]: u1 = v.cruz(w)

          In [68]: u1.x, u1.y, u1.z

       Mientras que :math:`\vec{w} \times \vec{v}` es:

       .. ipython::

          In [65]: u2 = w.cruz(v)

          In [68]: u2.x, u2.y, u2.z

  * Redefinir la clase anterior para que en lugar de los atributos, ``x``,
    ``y``, y ``z``, tenga uno sólo llamado ``coord``, que sea una lista de tres
    elementos. También redefinir los métodos según esto.

    *Sugerencia*: En el método ``__init__`` revisar que la lista que se va a
    guardar en ``coord`` tenga **exactamente** tres elementos. Si tiene más o 
    menos, asignarle a ``coord`` una lista vacía.

  * Definir una clase ``Tiempo`` para representar una hora del día, que tenga
    las siguientes condiciones (Tomado de *Aprenda a pensar como un programador
    con Python*):

    .. ipython::
       :suppress:

       In [1]: class Tiempo:
          ...:     def __init__(self, horas, minutos, segundos):
          ...:         self.h = horas
          ...:         self.m = minutos
          ...:         self.s = segundos
          ...:     def imprimir_tiempo(self):
          ...:         if self.h < 10:
          ...:             imprimir_h = '0' + str(self.h) + ':'
          ...:         else:
          ...:             imprimir_h = str(self.h) + ':'
          ...:         if self.m < 10:
          ...:             imprimir_m = '0' + str(self.m) + ':'
          ...:         else:
          ...:             imprimir_m = str(self.m) + ':'
          ...:         if self.s < 10:
          ...:             imprimir_s = '0' + str(self.s)
          ...:         else:
          ...:             imprimir_s = str(self.s)
          ...:         print imprimir_h + imprimir_m + imprimir_s
          ...:     def sumar(self, t):
          ...:         suma_s = (self.s + t.s)%60
          ...:         suma_m = (self.m + t.m)%60
          ...:         suma_h = (self.h + t.h)%24
          ...:         if self.s + t.s >= 60:
          ...:             suma_m += 1
          ...:         if self.m + t.m >= 60:
          ...:             suma_h += 1
          ...:         return Tiempo(suma_h,suma_m,suma_s)
          ...:

    1. Tres atributos: ``h``, ``m`` y ``s``, para guardar las horas, minutos y
       segundos.

    2. Un método llamado ``imprimir_tiempo`` que imprima el tiempo almacenado
       en una instancia, de la siguiente forma:

       .. ipython::

          In [117]: t1 = Tiempo(16,7,1)

          In [118]: t1.imprimir_tiempo()

          In [120]: t2 = Tiempo(2,6,32)

          In [121]: t2.imprimir_tiempo()

    3. Un método ``sumar`` que sume dos tiempos diferentes.

       *Sugerencias*:

       - Sumar cada atributo por separado, es decir, segundo con segundos,
         minutos con minutos y horas con horas.

       - Para obtener el resultado de los segundos y los minutos, la suma debe
         realizarse módulo 60. Por ejemplo, si un Tiempo tiene 50 segundos y
         otra 15, su suma **no** debe darnos 65 sino 5, lo que se obtiene
         como::

           (50 + 15)%60 = 5
         
         Para las horas, tomar la suma módulo 24.

       - Verificar si la suma de los segundos, **sin** tomar el módulo, es
         mayor o igual a ``60``, y si lo es, incrementar en ``1`` el valor de
         los minutos. Tener en cuenta lo mismo para la suma de los minutos y el
         valor de las horas.

       Un ejemplo de este método es:

       .. ipython::

          In [126]: t1 = Tiempo(23,50,45)

          In [127]: t2 = Tiempo(3,40,40)

          In [131]: t3 = t1.sumar(t2)

          In [132]: t3.imprimir_tiempo() 



..  LocalWords:  Python print Run LocalWords warning from future import math In
..  LocalWords:  division Mathematica image png kill img run ipython verbatim
..  LocalWords:  slicing return def suppress Out in elif else if range False li
..  LocalWords:  True append while for class init self split Imagenes
