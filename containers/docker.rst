Docker
======

How to — Alpine images
::::::::::::::::::::::

.. code-block:: docker

    RUN apk --update add --no-cache --virtual .builddeps \
                         build-base ... all build deps ... \
        && ... all run steps requiring build deps ...
        && apk del .builddeps



Related Tools
:::::::::::::

* :wiki:`Containers/Docker/Rocker`


Misc
::::

Container related stuff : https://www.mindmeister.com/fr/389671722/open-container-ecosystem-formerly-docker-ecosystem
