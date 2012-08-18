.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

===========================
Una simulación más realista
===========================

En la simulación que se ha desarrollado hasta el momento, la bola nunca deja de
rebotar y siempre regresa a la misma altura, lo cual no es lo que ocurre en la
realidad.

Para hacer que la simulación corresponda al comportamiento que normalmente
observamos en la caída de una bola, debemos incluir dos factores adicionales,
que son los que vamos a describir a continuación.

.. _friction:

Fuerza de arrastre o de fricción con el aire
--------------------------------------------

Ya que el aire es un fluido, la bola pierde parte de su velocidad mientras lo
atraviesa. Esto es lo que produce que paulatinamente se vaya deteniendo. En
Física este fenómeno se describe mediante una fuerza de arrastre, que se define
como:

.. math::

   F = -b \, v

donde *b* es una constante entre 0 y 1, que depende de las propiedades del
fluido y de las dimensiones del objeto que lo atraviesa, y *v* es la velocidad
del mismo.

Para incluir esta fuerza en la simulación, ya no puede considerarse a la
aceleración como constante e igual a la gravedad. En cambio de calcularse
mediante la ecuación:

.. math::

   a_{i+1} = g - b \, v_{i}


Ejercicios
~~~~~~~~~~

#. Incluir la fuerza de arrastre en la simulación de la caída de una bola. Para
   ello debe definirse una nueva lista llamada ``aceleraciones``, cuyo primer
   elemento va a ser *g* y los demás se van a calcular con la ecuación
   anterior.

   Calcular las velocidades con el método de Euler, como

   .. math::

      v_{i+1} = v_{i} + a_{i} \, \Delta t

   .. note::

      Tomar ``b`` menor a 0.7

#. Obtener una gráfica de la aceleración vs. el tiempo, así como nuevas
   gráficas para la posición y la velocidad. ¿Que cambió ahora?


Colisión inelástica
-------------------

Cuando un objeto choca contra otro, su velocidad después del choque no es
exactamente igual a la que llevaba antes, sino que disminuye en una pequeña
fracción debido a que el impacto absorbe parte de la energía cinética del golpe
y la transforma en calor.

En Física este fenómeno se describe haciendo que la velocidad después del
choque sea ligeramente menor que la velocidad antes del mismo, así:

.. math::

   v_{despues} = - k \, v_{antes}

donde *k* es una constante entre 0 y 1, que depende de las propiedades del
material que compone a los objetos que chocan.


Ejercicios
~~~~~~~~~~

#. Incluir la ecuación de colisión inelástica en la simulación de la bola.

   .. note::

      Tomar ``k`` mayor a 0.8

#. Hacer que la velocidad de la partícula sea cero, si el valor absoluto de la
   misma llega a ser menor que cierto valor muy pequeño. De esta forma
   conseguiremos que se detenga definitivamente.



..  LocalWords:  math inelástica Euler friction
