Amazon Web Services (AWS)
=========================

Amazon EC2
::::::::::



Amazon S3
:::::::::



Amazon Lambda
:::::::::::::

List of tools to review about writing/versionning/testing/releasing/deploying code on AWS Lambda. For now, only a rude list of links. 

* https://github.com/garnaat/kappa
* http://www.mot.la/2014-12-07-amazon-lambda-best-practices-development-and-deployment.html
* https://github.com/rebelmail/node-lambda
* https://github.com/rebelmail/node-lambda-template

Amazon Cloudfront
:::::::::::::::::

You can configure ngx_pagespeed to work with cloudfront:

.. code-block:: nginx

    pagespeed on;
    pagespeed FileCachePath /var/ngx_pagespeed_cache;
    pagespeed Domain http://romain.dorgueil.net/;
    pagespeed MapRewriteDomain d3nxtp0ub5fopc.cloudfront.net romain.dorgueil.net;
