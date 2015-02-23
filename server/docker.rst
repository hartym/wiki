Docker
======


.. code-block:: shell

    docker images --no-trunc| grep none | awk '{print $3}' | xargs docker rmi

* http://blog.benhall.me.uk/2015/01/boot2docker-runs-disk-space/
* http://jimhoskins.com/2013/07/27/remove-untagged-docker-images.html
* https://gist.github.com/irgeek/afb2e05775fff532f960
