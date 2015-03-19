Shell script
============



Cookbook
::::::::

Detect path of current script
-----------------------------

.. code-block:: shell

    __PATH__=$(cd $(dirname "$0"); pwd)
