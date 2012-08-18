.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

=============================
Movimiento en dos dimensiones
=============================

En Física, el movimiento en dos o más dimensiones se descompone como
movimientos diferentes, que evolucionan en cada dimensión por separado. En esta
sección vamos a apreciar como se modelan dos fenómenos de este tipo.


Tiro parabólico
---------------

De sus cursos de física seguramente recordarán que el tiro parabólico consiste
en el lanzamiento de un objeto con cierto inclinación con respecto al eje x,
cuya trayectoria forma una parábola. Este movimiento se compone a su vez de dos
movimientos separados:

  #. En el eje *x* el objeto se mueve con velocidad constante.

  #. En el eje *y* el objeto se mueve con aceleración constante.

Las ecuaciones que describen este fenómeno son:

.. math::
   :label: tiro

   x(t) = x_{0} + v_{0x} t

   y(t) = y_{0} + v_{0y} t + \frac{1}{2} g t^2

donde :math:`v_{0x}` y :math:`v_{0y}` son las velocidades iniciales en *x* e
*y* respectivamente, las cuales se calculan con las fórmulas:

.. math::
   :label: cond-ini

   v_{0x} = v_{0} \times \cos \theta

   v_{0y} = v_{0} \times \sin \theta

siendo :math:`v_{0}` la magnitud del vector velocidad inicial.

Con estos datos vamos a simular el tiro parabólico, a través de los ejercicios
que aparecen a continuación.

Ejercicios
~~~~~~~~~~

#. Crear un programa que calcule la evolución de un objeto que siga las
   ecuaciones :eq:`tiro`, con el método de Verlet.

   .. note::

      * Crear dos listas ``posiciones_x`` y ``posiciones_y``, para guardar las
        posiciones en cada eje de coordenadas.

      * Para obtener las nuevas posiciones en *y*, usar el mismo código que se
        usó para la caída de la bola, pero cambiando la posición y velocidad
        iniciales, según la ecuación :eq:`cond-ini`

        Además, cambiar el nombre de ``velocidades``  a ``velocidades_y``.

      * Para obtener las nuevas posiciones en *x*, no es necesario determinar
        nuevas velocidades y añadirlas a ``velocidades_x``, porque la velocidad
        es *constante*. En otras palabras, estas nuevas posiciones deben
        calcularse como:

        .. math::

           x_{i+1} = x_{i} + v_{0x} \, \Delta t

#. Hacer una animación con VPython de este sistema dinámico.

..  LocalWords:  math LocalWords cos theta label eq Verlet VPython cond ini
