Selenium
========

Python recipes
::::::::::::::

How to get the HTML of one element?
-----------------------------------

.. code-block:: python

    element.get_attribute('innerHTML')

How to get the next sibling of an element?
------------------------------------------


.. code-block:: python

    el = browser.find_element_by_xpath('//...')
    next_el = el.find_element_by_xpath('following-sibling::*[1]')
    
    
