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

How to make sure a given element is visible?
--------------------------------------------

Some frontend frameworks will refuse clicks from the user if the element clicked on is not visible. Here is a little trick that
ensure the element is in fact visible, by scrolling down below it then scrolling back up a bit, before you do click on it
using your robot.


.. code-block:: python

    el = find_element()  # replace this by whatever element finder you need
    browser.execute_script("arguments[0].scrollIntoView(true); window.scrollBy(0, -120);", el)
    
