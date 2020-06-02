Secure Sockets Layer (SSL)
==========================

Certificates
::::::::::::

* `Création de certificat + CA + auto-signature <http://www.linux-france.org/prj/edu/archinet/systeme/ch24s03.html>`_ (FR)

Read certificate chain with openssl

.. code-block:: shell

   openssl s_client -showcerts -servername www.google.com -connect www.google.com:443 </dev/null
   
   
