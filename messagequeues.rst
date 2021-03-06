Message Queues
==============

AMQP
::::

* https://www.rabbitmq.com/tutorials/amqp-concepts.html

RabbitMQ
::::::::

Concepts: https://medium.com/faun/rabbitmq-connection-vs-channel-aed1188a7f3a

* Channels: https://www.rabbitmq.com/channels.html
* Queues: https://www.rabbitmq.com/queues.html

https://www.cloudamqp.com/blog/2015-09-03-part4-rabbitmq-for-beginners-exchanges-routing-keys-bindings.html

Configuration and authentication
--------------------------------

Create users and virtual hosts:

.. code-block:: shell-session

    RMQ_USERNAME=rmq_user
    RMQ_PASSWORD=s3cr3tp4ssw0rd
    RMQ_VHOST=rmq_vhost
    rabbitmqctl add_user $RMQ_USERNAME $RMQ_PASSWORD
    rabbitmqctl add_vhost $RMQ_VHOST
    rabbitmqctl set_permissions -p $RMQ_VHOST $RMQ_USERNAME ".*" ".*" ".*"
    
This is not persistent, will only live for the lifetime of the container. (todo: find documentation about this?)

Using the official docker image (https://hub.docker.com/_/rabbitmq/), we can use an undocumented feature:
the entrypoint will read `/etc/rabbitmq/definitions.json` if it exists and use it to define entities in rabbitmq,
so if we derive our image from that adding this file, it will auto add them. 

Definitions file (`/etc/rabbitmq/definitions.json`):

.. code-block:: json

    {       
        "users":[
                {"name":"rmq_user","password_hash":"...","tags":""},
                {"name":"rmq_admin","password_hash":"...","tags":"administrator"}
        ],
        "vhosts":[
                {"name":"/"}
        ],
        "permissions":[
                ...
        ],
        "parameters":[],
        "policies":[
                ...
        ],
        "queues":[
                ...
        ],
        "exchanges":[
                ...
        ],
        "bindings":[
                ...
        ]
    }

TODO: WIP BELOW

To generate this file from current configuration, you need `rabbitmqadmin` script, which uses RMQ management plugin.

Official docker image provides the plugin it if the "management" tag is used.

kubectl port-forward rabbitmq-54644f7685-gf8hw 15672:15672

open http://localhost:15672/

guest:guest (default)

Dump


Clients
-------

* https://aio-pika.readthedocs.io/
* https://github.com/mosquito/aiormq


Topology
--------

Exchange to exchange bindings
.............................

* https://www.rabbitmq.com/e2e.html
* https://www.rabbitmq.com/blog/2010/10/19/exchange-to-exchange-bindings/
* https://skillachie.com/2014/06/27/rabbitmq-exchange-to-exchange-bindings-ampq/

* (not convinced about the followin ...) https://quentinkaiser.be/security/tool/2017/08/28/cottontail-release/
