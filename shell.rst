Shell script
============

.. image:: http://turnoff.us/image/en/bash-on-windows.png

    Image: http://turnoff.us/image/en/bash-on-windows.png


Cookbook
::::::::

Detect path of current script
-----------------------------

.. code-block:: shell

    __PATH__=$(cd $(dirname "$0"); pwd)

Date aliases
------------

.. code-block:: shell

    alias isodate='date +%Y-%m-%dT%H:%M:%S%z'
