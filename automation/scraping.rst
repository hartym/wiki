Web Scraping
============

Basic Tools
:::::::::::

These tools do not use a real browser, so they're perfect for scrapping standards-based websites, but you may hit a wall trying to
scrap sites that abuse scripting (angular or react client only sites, other single page applications ...).

* Scrapy (https://scrapy.org/)
* Requests (http://docs.python-requests.org/)
* :wiki:`Automation/Scraping/BeautifulSoup`

Less Basic Tools
::::::::::::::::

These tools actually run in your own browser. 

* `WebScraper <http://webscraper.io/>`_ and its `chrome extension <https://chrome.google.com/webstore/detail/web-scraper/jnhgnonknehpejjnehehllkliplmbmhn>`_


Ninja Tools
:::::::::::

These tools will allow to run a scripted browser in the background, or even on a remote server or server farm. If you're doing
serious web-stealing/fuck-your-content work, then you should go here.

* :wiki:`Python/Jupyter`
* :wiki:`Automation/Scraping/Selenium`
* CouchDB
* :wiki:`Automation/Scraping/Bonobo` (wip)
* http://phantomjs.org/ & http://casperjs.org/
* Diggernaut (https://www.diggernaut.com/) + free web scrapers repository (https://github.com/Diggernaut/configs)

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
