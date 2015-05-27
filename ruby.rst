Ruby
====

* Install nokogiri and nokogumbo in OSX


.. code-block:: shell

    brew install libxml2 libxslt
    ARCHFLAGS="-arch x86_64" bundle exec gem install nokogiri
    ARCHFLAGS="-arch x86_64" bundle exec gem install nokogumbo
