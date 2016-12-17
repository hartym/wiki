Jupyter
=======

Jupyter (or IPython) Notebooks
::::::::::::::::::::::::::::::

Tips and tricks
---------------

Autoreload
..........

.. code-block:: python

    %load_ext autoreload
    %autoreload 2
    
Reference: http://ipython.readthedocs.io/en/stable/config/extensions/autoreload.html

Install a package without stopping the kernel
.............................................

(or run any shell command from within a notebook)

.. code-block:: python

    !pip install bokeh
    
