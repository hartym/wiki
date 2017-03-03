Python
======

Python is a widely used high-level, general-purpose, interpreted, dynamic programming language.

Its design philosophy emphasizes code readability, and its syntax allows programmers to express concepts in fewer lines of code than possible in languages such as C++ or Java.

Web development
:::::::::::::::

Forms
-----

There are two easy ways of creating, displaying, validating and normalizing web forms and web forms data in python (afaik).
If you're using django, you probably want to use :wiki:`Python/DjangoForms`. If you're not using django, the only serious form framework
I found until then is :wiki:`Python/WTForms`.

* :wiki:`Python/DjangoForms`
* :wiki:`Python/WTForms`

Frameworks and toolkits
-----------------------

* :wiki:`Python/Django`
* :wiki:`Python/Aiohttp`
* :wiki:`Python/Tornado`

Authentication (JWT, OAuth, ...)
--------------------------------

* Python-Social-Auth: http://psa.matiasaguirre.net/ (with web framework adapters)
* RAuth: https://rauth.readthedocs.org/en/latest/
* JSON Web Tokens: https://pyjwt.readthedocs.io/en/latest/

Cookbook
::::::::

.. code-block:: python

    __path__ = os.path.dirname(os.path.join(os.getcwd(), __file__))

* OrderedDict subclass implementing insertion methods to adjust the order: https://gist.github.com/jaredks/6276032

PyEnv
:::::

Install python3 on recent OSX with working Sqlite3 and OpenSSL
--------------------------------------------------------------

.. code-block:: shell

    CFLAGS="-I$(brew --prefix openssl)/include -I$(brew --prefix sqlite)/include" LDFLAGS="-L$(brew --prefix openssl)/lib -L$(brew --prefix sqlite)/lib" pyenv install -v 3.6.0

Misc
::::

* Magic methods: http://www.rafekettler.com/magicmethods.html
* Coroutines: http://www.dabeaz.com/coroutines/Coroutines.pdf
* Asyncio cheat sheet: https://www.pythonsheets.com/notes/python-asyncio.html
* Graphs, digraphs, hypergraphs

  * https://www.python.org/doc/essays/graphs/
  * https://networkx.readthedocs.io/
  * https://github.com/pmatiello/python-graph (old but looks simple and powerfull)
  
Dependency Injection and Inversion of Control
---------------------------------------------

Python, by its nature, does not justify using and IoC/DI container most of the time, but it can still be useful
in some cases.

Some searches about the state of the art ... (no opinion on the various libraries yet)

* https://github.com/google/pinject
* https://github.com/ets-labs/python-dependency-injector
* Zope Component Architecture: http://muthukadan.net/docs/zca.html & http://zopecomponent.readthedocs.io/en/latest/

