Django
======

Django is an open-source web framework, written in Python, which follows the model-view-template (MVT) architectural pattern, which is just a name variant of MVC.

Django's primary goal is to ease the creation of complex, database-driven websites. Django emphasizes reusability and "pluggability" of components, rapid development, and the principle of don't repeat yourself. Python is used throughout, even for settings files and data models. Django also provides an optional administrative create, read, update and delete interface that is generated dynamically through introspection and configured via admin models.

Recipes
:::::::

How to add created/updated fields to django models
--------------------------------------------------

.. code-block:: python

    class MyTimestampedModel(models.Model):
        # ... other fields ...
        created_at = models.DateTimeField(auto_now_add=True)
        updated_at = models.DateTimeField(auto_now=True)

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

* :wiki:`Python/Django/Authentication`
* :wiki:`Python/DjangoForms`

