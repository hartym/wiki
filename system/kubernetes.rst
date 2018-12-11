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

Cookbook
::::::::

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



