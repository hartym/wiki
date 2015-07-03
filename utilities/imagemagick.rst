ImageMagick (and GraphicsMagick)
================================

.. code-block:: shell

    for i in *; do convert -resize 1800x $i -quality 80 ../bgo/$i; done
