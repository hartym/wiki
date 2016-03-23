Web Scraping
============

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

