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
    
How to fill in a login / password form (or any other form)?
-----------------------------------------------------------

.. code-block:: python

    username = browser.find_element_by_id('username')
    username.send_keys('thatsme')
    password = browser.find_element_by_id('password')
    password.send_keys('s3cr3t')
    form = browser.find_element_by_id('signin-form')
    form.submit()


