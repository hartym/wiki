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
* http://fr.slideshare.net/AmazonWebServices/aws-lambda-eventdriven-code-in-the-cloud-50364719
* https://aws.amazon.com/fr/blogs/compute/new-deployment-options-for-aws-lambda/
* https://aws.amazon.com/fr/blogs/compute/category/aws-lambda/


Amazon Cloudfront
:::::::::::::::::

You can configure ngx_pagespeed to work with cloudfront:

.. code-block:: nginx

    pagespeed on;
    pagespeed FileCachePath /var/ngx_pagespeed_cache;
    pagespeed Domain http://romain.dorgueil.net/;
    pagespeed MapRewriteDomain d3nxtp0ub5fopc.cloudfront.net romain.dorgueil.net;
    
Identity and Access Management (IAM)
::::::::::::::::::::::::::::::::::::

Policy to access an S3 bucket (or many buckets).

.. code-block:: json

    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "s3:ListBucket"
                ],
                "Resource": [
                    "arn:aws:s3:::some-buckets-*-dev"
                ]
            },
            {
                "Effect": "Allow",
                "Action": [
                    "s3:PutObject",
                    "s3:GetObject"
                ],
                "Resource": [
                    "arn:aws:s3:::some-buckets-*-dev/*"
                ]
            }
        ]
    }
