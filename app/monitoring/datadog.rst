Datadog
=======

CoreOS unit to run agent
::::::::::::::::::::::::

.. code-block:: ini

    [Unit]
    Description=Monitoring Service
    
    [Service]
    TimeoutStartSec=0
    ExecStartPre=-/usr/bin/docker kill dd-agent
    ExecStartPre=-/usr/bin/docker rm dd-agent
    ExecStartPre=/usr/bin/docker pull datadog/docker-dd-agent
    ExecStart=/usr/bin/bash -c \
      "/usr/bin/docker run --privileged --name dd-agent -h `hostname` \
      -v /var/run/docker.sock:/var/run/docker.sock \
      -v /proc/mounts:/host/proc/mounts:ro \
      -v /sys/fs/cgroup/:/host/sys/fs/cgroup:ro \
      -v /home/core/dd-agent:/etc/dd-agent:ro \
      -e API_KEY=XXX_API_KEY_HERE_XXX \
      datadog/docker-dd-agent"
    
    [X-Fleet]
    Global=true
