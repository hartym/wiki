ImageMagick (and GraphicsMagick)
================================

* https://en.wikipedia.org/wiki/ImageMagick
* http://www.imagemagick.org/script/index.php
* https://en.wikipedia.org/wiki/GraphicsMagick
* http://www.graphicsmagick.org/

.. code-block:: shell

    for i in *; do convert -resize 1800x $i -quality 80 ../bgo/$i; done
