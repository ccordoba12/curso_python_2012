.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

==========================
Una simulación más precisa
==========================

A fin de obtener una simulación más precisa es necesario utilizar un método
distinto al de Euler, ya que éste acumula muchos errores a medida que
transcurre el tiempo.

Uno de estos métodos se conoce como método de `Verlet
<http://en.wikipedia.org/wiki/Verlet_integration>`_ en las velocidades, el cual
se define mediante las siguientes ecuaciones:

.. math::

   v_{i+1} = v_{i} + \left( a_{i} + a_{i+1} \right) \frac{\Delta t}{2}

   x_{i+1} = x_{i} + v_{i} \Delta t + a_{i} \frac{\Delta t^2}{2}

Los términos adicionales que incluyen tanto :math:`v_{i+1}` como
:math:`x_{i+1}`, hacen que el cómputo de estos valores sea mucho más
**preciso** que para el método de Euler, como lo veremos a continuación.


Ejercicios
~~~~~~~~~~

#. Programar la caída de una bola **sin** fuerza de arrastre y **sin** colisión
   inelástica, usando el método de Verlet.

   .. note::
   
     * Calcular primero la nueva posición y añadirla a la lista de posiciones.

     * No utilizar una lista de aceleraciones, ya que la aceleración es
       constante e igual a *g*.

     * Debido a lo anterior, la ecuación para la velocidad en el siguiente
       instante se reduce a:

       .. math::
     
          v_{i+1} = v_{i} + g \, \Delta t

       Calcular la nueva velocidad con esta ecuación.

#. Realizar una gráfica de la posición vs. el tiempo, y trazar una línea
   horizontal a la altura de la posición inicial. Comparar esta gráfica con la
   que se obtuvo usando el método de Euler.

#. Programar la caída de la bola de la bola **con** fuerza de arrastre y
   colisión inelástica, usando el método de Verlet.

   .. note::

      * Calcular primero la nueva posición y añadirla a la lista de posiciones.

      * Calcular la nueva aceleración y añadirla a la lista de
        aceleraciones. Usar la fórmula de la sección :ref:`friction`.

      * Finalmente, calcular la nueva velocidad. No olvidar generar una
        colisión inelástica cuando la bola chocha contra el piso.


..  LocalWords:  Euler Verlet math LocalWords left right inelástica dt ref
..  LocalWords:  friction
