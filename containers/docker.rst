Docker
======

Cleanup
:::::::

.. code-block:: shell

    docker images --no-trunc| grep none | awk '{print $3}' | xargs docker rmi

* http://blog.benhall.me.uk/2015/01/boot2docker-runs-disk-space/
* http://jimhoskins.com/2013/07/27/remove-untagged-docker-images.html

Security and custom certificate authorities
:::::::::::::::::::::::::::::::::::::::::::

* https://gist.github.com/irgeek/afb2e05775fff532f960

Boot2Docker / Docker machine on OSX
:::::::::::::::::::::::::::::::::::

No space left
-------------

Kill all, recreate a machine with more disk. Way more efficient than trying to resize the virtual machine disk.

.. code-block:: shell

    docker-machine create --virtualbox-disk-size 50000 -d virtualbox dev
    
