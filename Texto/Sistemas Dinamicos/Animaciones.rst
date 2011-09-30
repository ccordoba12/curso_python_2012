.. -*- mode: rst; mode: flyspell; mode: auto-fill; mode: wiki-nav-*-


===============================================
Generar gráficas y animaciones de la simulación
===============================================

Para poder apreciar si la simulación está funcionando correctamente, lo mejor
que puede hacerse es visualizar la forma en que está evolucionando a través de
gráficas y animaciones.

En Python esto puede hacerse por medio de dos librerías:

Matplotlib
----------

Matplotlib ha sido ideada para generar gráficas bidimensionales de alta
calidad. Para cargar la librería usamos el comando::

  import matplotlib.pyplot as plt

``pyplot`` es un submódulo de Matplotlib y por costumbre se importa con el
nombre corto ``plt``. Dentro de este módulo, el comando que más vamos a
utilizar es ``plot``, que tiene la siguiente sintaxis::

  plt.plot(x, y)

donde ``x`` es una lista que contiene los datos que se van a graficar en el eje
**x**, mientras que ``y`` contienen los del eje **y**.

.. note::

   Para que ``plot`` funcione correctamente, las dos listas deben tener el
   mismo número de elementos.

Por ejemplo, para graficar la línea vertical :math:`y=2` podemos usar el comando:

  .. ipython::
     
     @suppress
     In [1]: import matplotlib.pyplot as plt

     @savefig 1.png width=5.5in
     In [2]: plt.plot([2]*10, range(10))

``plot`` también puede recibir una sola lista como argumento, en cuyo caso toma
esta lista como ``y``, mientras que utiliza ``x`` automáticamente como
``range(0, len(y))``. Por ejemplo:

  .. ipython::

     In [1]: plt.cla()

     @savefig 2.png width=5.5in
     In [2]: plt.plot(range(5,10))

.. note::

   ``cla()`` se utiliza para limpiar la región de la gráfica antes de volver
   pintar sobre ella nuevamente.

Este método también puede usarse para generar una línea horizontal como:

  .. ipython::

     In [1]: plt.cla()

     @savefig 3.png width=5.5in
     In [2]: plt.plot([3]*5)

Ejercicios
~~~~~~~~~~

  #. Usar ``plot`` para graficar obtener una gráfica de la posición de la bola
     vs. el tiempo, y otra de la velocidad vs. el tiempo.

  #. Graficar una línea horizontal a la altura de la posición inicial y dejar
     evolucionar el sistema durante al menos 20 segundos. Tratar de entender
     qué es lo que está pasando en este caso.

VPython
-------

VPython es una librería para hacer animaciones tridimensionales en OpenGL. Para
cargar la librería usamos el comando::

  import visual as vis

Antes de proceder a añadir objetos a la animación, es necesario crear una
escena, y definir algunas propiedades de la misma, de la siguiente manera::

  escena = vis.display(title='Caída de una bola')   # Crea la escena
  escena.exit = False                               # Evita que al cerrar la ventana se cierre la consola
  escena.visible = True                             # Hace visible la escena
  escena.select()                                   # Selecciona la escena para añadirle objetos
  escena.autoscale = False                          # Evita que se reajuste el tamaño de la escena a medida que avanza la simulación

Después de esto podemos pasar a añadirle una caja, que va representar el suelo,
de la siguiente forma::

  piso = vis.box(pos=(0, 0, 0), length=4, height=0.5, width=4, color=vis.color.blue)

.. Añadir que son pos, length, height y width.

Después añadimos una esfera que va a representar la bola como::

  bola = vis.sphere(pos=(0, p0, 0), radius=1, color=vis.color.red)

``bola`` tiene un atributo ``pos`` que define su posición en el espacio y que
vamos a actualizar con la lista de ``posiciones`` para llevar a cabo la
animación. Por ejemplo, para cambiar la posición de la bola al primer lugar de
``posiciones`` usamos el comando::

  bola.pos = vector(0, posiciones[0], 0) 

Ejercicios
~~~~~~~~~~

.. warning::

   Para poder correr simulaciones hechas con VPython con Spyder debe irse al
   menú :menuselection:`Run --> Open Interpreter`, para abrir un tipo especial
   de terminal que nos permita correr las animaciones.

   .. Tener en cuenta para el próximo semestre!!
   ..  #. Ir al menú :menuselection:`Tools --> Preferences --> Console --> External
   ..  Modules --> PyQt` y desactivar la opción que dice :menuselection:`Replace
   ..  PyQt' input hook`

#. Realizar la animación completa de la trayectoria de la bola, usando un ciclo
   ``for``.

   .. note::

      Usar ``vis.rate(n)`` (donde ``n`` es un número entero) dentro del ciclo
      ``for`` para no tener que graficar todas las posiciones sino sólo unas
      cuantas. Experimentar con varios valores ``n`` para ver cuál es el que
      mejor se ajusta.

#. Hacer que el borde inferior de la bola sea el que choque contra el suelo y
   no su centro, como está sucediendo hasta el momento.

..  LocalWords:  math LocalWords Python Euler dt label euler for if Matplotlib
..  LocalWords:  VPython import matplotlib pyplot plt plot graficar range png
..  LocalWords:  ipython savefig suppress width in cla vs warning
