Django
======

Recipes
:::::::

How to add created/updated fields to django models
--------------------------------------------------

.. code-block:: python

    class MyTimestampedModel(models.Model):
        # ... other fields ...
        created_at = models.DateTimeField(auto_now_add=True)
        updated_at = models.DateTimeField(auto_now=True)

Requirements
::::::::::::

Basics
------

* Django>=1.8,<1.9
* django-jinja
* django-pipeline>=1.5,<1.6

PostgreSQL
----------

* psycopg2
* django-pgjson

Requests
--------

* requests[security]
* requests-cache

E-mails
:::::::

Settings
--------

.. code-block:: python

    EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
    EMAIL_DEFAULT_FROM = '...'
    EMAIL_HOST = 'smtp.example.com'
    EMAIL_HOST_USER = '...'
    EMAIL_HOST_PASSWORD = '...'
    EMAIL_USE_TLS = True
    EMAIL_PORT = 587
    
Related
:::::::

* :wiki:`Python/DjangoForms`
