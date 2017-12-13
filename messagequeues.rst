Message Queues
==============

RabbitMQ
::::::::

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
    

