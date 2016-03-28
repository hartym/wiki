Docker
======

Docker Machine
::::::::::::::

No space left
-------------

Kill the box, recreate a machine with more disk. Way faster than trying to resize the virtual machine disk.

.. code-block:: shell

    docker-machine create --virtualbox-disk-size 50000 -d virtualbox dev


Security and custom certificate authorities
:::::::::::::::::::::::::::::::::::::::::::

* https://gist.github.com/irgeek/afb2e05775fff532f960


Misc
::::

Container related stuff : https://www.mindmeister.com/fr/389671722/open-container-ecosystem-formerly-docker-ecosystem
