Web Scraping with Bonobo (WIP)
==============================

* See also :wiki:`Python/Bonobo`
* https://github.com/python-bonobo/bonobo

Example
:::::::

.. code-block:: python

    from bonobo.ext.jupyter import jupyter_run
    from bonobo.ext.selenium import browser
    from bonobo import inject
    from bonobo.util import log
    from bs4 import BeautifulSoup, Comment
    
    @inject(browser)
    def open(browser):
        browser.get('http://perdu.com/')
    
    jupyter_run(open, ..., log)
