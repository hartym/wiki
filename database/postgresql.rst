PostgreSQL
==========

Measuring
:::::::::

How much disk space is some relation (table, index, ...) taking ?
-----------------------------------------------------------------

You can use pg_relation_size():

.. code-block:: sql

    select pg_relation_size('some_table_or_idx');

It's way better to be able to actually read the result:

.. code-block:: sql

    select pg_size_pretty(pg_relation_size('some_table_or_idx'));
    
More info and scripts: https://wiki.postgresql.org/wiki/Disk_Usage

Tuning
::::::

Tuning the filesystem
---------------------

* https://blog.pgaddict.com/posts/postgresql-performance-on-ext4-and-xfs
* https://fr.slideshare.net/fuzzycz/postgresql-on-ext4-xfs-btrfs-and-zfs

Wasted space & vacuuming
------------------------

* https://www.citusdata.com/blog/2017/10/20/monitoring-your-bloat-in-postgres/
* https://jobs.zalando.com/tech/blog/achieving-correct-bloat-estimates-of-json-data-in-postgresql/

About JSONB
-----------

* https://heap.io/blog/engineering/when-to-avoid-jsonb-in-a-postgresql-schema
* https://www.citusdata.com/blog/2016/07/14/choosing-nosql-hstore-json-jsonb/

Backup & Restore
----------------

Simple backup command:

.. code-block:: shell

    pg_dump --format=c --role=<role> <dbname>
    
Simple restore command:

.. code-block:: shell

    pg_restore --role=<role> -d <dbname> <filename>

Tools
:::::

Visualize explain analyze results: https://explain.depesz.com/

Misc.
:::::

A few links ...

* https://www.cybertec-postgresql.com/en/postgresql-speeding-up-group-by-and-joins/

