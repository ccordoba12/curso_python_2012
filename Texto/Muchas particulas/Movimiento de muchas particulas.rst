.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-

===============================
Movimiento de muchas partículas
===============================

Para simular el movimiento de muchas partículas al mismo tiempo, vamos a seguir
el mismo procedimiento de la sección anterior. Es decir, sólo vamos a cambiar
los valores de las posiciones, velocidades y aceleraciones iniciales, mientras
que dejamos lo demás exactamente como estaba, pues los arreglos de Numpy se van
a encargar de hacerlo todo por nosotros.

Así que para simular el movimiento de dos partículas, vamos a definir estos
valores como::

  p0 = np.array([[0, 5], [4, 5]])
  v0 = np.array([[2, 0], [-2, 0]])
  a0 = np.array([[0, g], [0, g]])

Lo que vemos es que ahora cada arreglo se compone de dos sub-arreglos, el
primero de los cuales corresponde a la posición, velocidad y aceleración de la
primera partícula, y el segundo a los mismos valores pero de la segunda
partícula.

Además de esto, lo único que diferencia el código de una partícula del de
muchas, es la adición de una función que calcule la colisión entre una
partícula y otra.

.. warning::

   Para la próxima clase! Sorry.

**Ejercicios**

#. Del programa escrito en la sección anterior, cambiar sólo la parte que
   genera la colisión con los muros.

#. Generar una animación en VPython. Para ello vamos a seguir estos pasos:

   * Con un ciclo ``for`` generar tantas partículas como se hayan definido en
     ``p0``. Utilizar para todas la definición en términos de ``vis.cylinder``,
     pero cambiándole sus posiciones.

   * Dentro del ciclo ``for`` que genera la animación, introducir un nuevo
     ciclo ``for`` para moverse en el arreglo de partículas.

   * Actualizar su posición como::

       particulas[i].pos = posicion[i]

     donde ``posicion`` es un elemento de ``posiciones``

..  LocalWords:  Numpy array np LocalWords sub
