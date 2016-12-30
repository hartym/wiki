SQLAlchemy
==========

TODO: This page is highly incomplete and needs a lot of work.

Reference: http://docs.sqlalchemy.org/en/rel_1_1/

Database Abstration Layer
:::::::::::::::::::::::::

.. code-block:: python

    from sqlalchemy import create_engine
    logging.basicConfig()
    logging.getLogger('sqlalchemy.engine').setLevel(logging.INFO)
    engine = create_engine('sqlite:///basics.sqlite')

Object Relational Mapper
::::::::::::::::::::::::


Miscellaneous
:::::::::::::

