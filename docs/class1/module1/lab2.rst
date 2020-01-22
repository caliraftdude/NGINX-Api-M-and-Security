Lab – Reviewing the network architecture
================================================================

.. NOTE:: It is important to understand the full architecture, network and application, in order to use the correct IP addresses and ports

- The microservices are running within a Kubernetes cluster that consists of a Master and two nodes.
- The services are deployed within Kubernetes in four individual pods.
- Each service is published by a KubeProxy on four different ports.
- NGINX+ API Gateways are running in Docker.  The External port is 8443 and the internal port is 443.

|image1.2.1|

.. |image1.2.1| image:: /_static/image001-2-1.png
