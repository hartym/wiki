Docker
======

Cleanup
:::::::

.. code-block:: shell

    docker images --no-trunc| grep none | awk '{print $3}' | xargs docker rmi

* http://blog.benhall.me.uk/2015/01/boot2docker-runs-disk-space/
* http://jimhoskins.com/2013/07/27/remove-untagged-docker-images.html
* https://gist.github.com/irgeek/afb2e05775fff532f960

Boot2Docker / Docker machine on OSX
:::::::::::::::::::::::::::::::::::

No space left
-------------

Resize the boot2docker mount

.. code-block:: shell

    cd .docker/machine/machines/machine-name
    vboxmanage clonehd $PWD/disk.vmdk $PWD/disk.vdi --format VDI --variant Standard

cf https://docs.docker.com/articles/b2d_volume_resize/
