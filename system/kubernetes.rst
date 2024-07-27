Kubernetes
==========

Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.

http://kubernetes.io/

Introduction: https://docs.google.com/presentation/d/1zrfVlE5r61ZNQrmXKx5gJmBcXnoa_WerHEnTxu5SMco

Books and readings
::::::::::::::::::

* Start with https://kubernetes.io/docs/tutorials/kubernetes-basics/
* https://github.com/kelseyhightower/kubernetes-the-hard-way/tree/master/docs
* https://github.com/hobby-kube/guide

Resources
:::::::::

* https://ramitsurana.github.io/awesome-kubernetes/

Benchmarks
::::::::::

* https://itnext.io/benchmark-results-of-kubernetes-network-plugins-cni-over-10gbit-s-network-updated-april-2019-4a9886efe9c4

Network
:::::::

* https://www.projectcalico.org/

Cookbook
::::::::

Environment from ConfigMap
--------------------------

.. code-block:: yaml

    envFrom:
    - configMapRef:
      name: eat-at-joe

Rollout / rollback using deployments
------------------------------------

Tip article: `How to rollout or rollback a deployment on a Kubernetes cluster? </blog/en/tips/2016/08/27/rollout-rollback-kubernetes-deployment.html>`_

Rollout
.......

.. code-block:: shell

    kubectl patch deployment $DEPLOYMENT \
            -p'{"spec":{"template":{"spec":{"containers":[{"name":"$CONTAINER","image":"$IMAGE"}]}}}}'

Rollback
........

.. code-block:: shell

    kubectl rollout undo deployment/$DEPLOYMENT [--to-revision 42]

Status
......

.. code-block:: shell

    kubectl rollout status deployment/$DEPLOYMENT
    
Restart
.......

.. code-block:: shell

    kubectl rollout restart deployment $DEPLOYMENT
    
Available since kubectl 1.15 (client side feature), will respect the deployment strategy.

Probes
::::::

**Liveness Probe**:

Checks if the application inside the container is still running. If the liveness probe fails, Kubernetes will restart the container.
Detects and recovers from situations where the application is stuck or deadlocked.

**Readiness Probe**

Checks if the application inside the container is ready to serve traffic.
If the readiness probe fails, the container is removed from the service's endpoints, meaning it will not receive any traffic.
Ensures that the application is fully initialized and ready to handle requests before sending traffic to it.

**Startup Probe**

Checks if the application inside the container has started successfully. If the startup probe fails, Kubernetes will restart the container. This probe is useful for applications that have a long initialization phase. Ensures that the application has successfully started before performing liveness and readiness checks.

**Example Configuration**

.. code-block:: yaml

    apiVersion: v1
    kind: Pod
    metadata:
      name: example-pod
    spec:
      containers:
      - name: example-container
        image: example-image
        livenessProbe:
          httpGet:
            path: /healthz
            port: 8080
          initialDelaySeconds: 3
          periodSeconds: 3
        readinessProbe:
          httpGet:
            path: /healthz/ready
            port: 8080
          initialDelaySeconds: 5
          periodSeconds: 5
        startupProbe:
          httpGet:
            path: /healthz/startup
            port: 8080
          initialDelaySeconds: 10
          periodSeconds: 10


Capacity Planning
-----------------

Poor-man's swiss-knife

.. code-block:: shell

    for rt in deploy daemonset; do
      echo $rt
      kubectl get $rt --all-namespaces -o json | \
        jq -r '.items[] | [.metadata.namespace, .metadata.name, .spec.replicas] + (.spec.template.spec.containers[] | [.name, .resources.requests.cpu, .resources.requests.memory ]) + [(.spec.template.spec.affinity.podAntiAffinity | @text) ] | @tsv'
      echo
    done


Google Cloud Platform (GCP)
---------------------------

Google Kubernetes Engine (GKE)
..............................

GKE is a managed Kubernetes cluster.

Checklist when things goes wrong:

* K8S: Ingress -> Service -> Deployment -> ReplicaSet -> Pod
* GC: Firewall rules matches the service exposed NodePort (describe service to get the port)
* GC: L7 router configuration is correct (backend, routes, frontend)
* GC: Health checks show green status.

Google Compute Engine (GCE)
...........................

Amazon Elastic Compute Cloude (EC2)
...................................

Amazon Elastic Container Service on Kubernetes (EKS)
....................................................

Scaleway
........

* https://github.com/NetzreichGmbH/scaleway-kubernetes
* https://chmod666.org/2017/11/Hosting-a-self-made-Kubernetes-infrastructure-on-Scaleway
* https://www.tauceti.blog/post/kubernetes-the-not-so-hard-way-with-ansible-at-scaleway-part-1/



