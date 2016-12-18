Pandas
======

Pandas is an open source, BSD-licensed library providing high-performance, easy-to-use data structures and data analysis tools
for the Python programming language.

Cookbook
::::::::

Setup notebook for pandas + bokeh
---------------------------------

.. code-block:: python

    import os
    import pandas as pd
    import numpy as np
    from bokeh.io import output_notebook, show

    # setup some globals we'll use as base paths
    BASE_DIR = os.path.realpath(os.path.join(os.getcwd(), '..'))
    DATA_DIR = os.path.join(BASE_DIR, 'data')

    # tell bokeh to output graphs in the notebook
    output_notebook()

    # depends on input data, but maybe handy to see untruncated data if you have a lot of columns
    pd.options.display.max_columns = 100

    # output the computed paths
    print('base:', BASE_DIR)
    print('data:', DATA_DIR)
    

Links and references
::::::::::::::::::::

* http://pandas.pydata.org/
* http://pandas.pydata.org/pandas-docs/stable/

See also
::::::::

* :wiki:`Python/Bokeh`

