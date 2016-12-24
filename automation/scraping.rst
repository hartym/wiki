Web Scraping
============

Basic Tools
:::::::::::

* Scrapy (https://scrapy.org/)
* Requests (http://docs.python-requests.org/)

Less Basic Tools
::::::::::::::

* http://webscraper.io/ (https://chrome.google.com/webstore/detail/web-scraper/jnhgnonknehpejjnehehllkliplmbmhn)
* http://phantomjs.org/ & http://casperjs.org/

Ninja Tools
:::::::::::

* :wiki:`Python/Jupyter`
* :wiki:`Scraping/Selenium`
* CouchDB
* :wiki:`Scraping/Bonobo` (wip)

Recipes
:::::::

Using Chrome Developper tools to autoload an infinite scrollable list
---------------------------------------------------------------------

.. code-block:: javascript

    function scrollDown() {
      window.scrollTo(0,document.body.scrollHeight)
    };
    $(document).ajaxSuccess(function() {
      scrollDown();
    });


Misc
::::

TODO:

* explore ZeroMQ to distribute work? Dask?
