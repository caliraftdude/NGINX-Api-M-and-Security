Lab – Reviewing the Kubernetes deployment
================================================================

-  Launch the Kubernetes dashboard from the UDF lab UI.  You will find the link under the **systems** column, K8S Master and under the **ACCESS** dropdown

|image1.4.1|

-  Review the deployments.  As you can see, the four microservices are up and running.

|image1.4.2|

-  Review the services.  Each microservice is published through a KubeProxy.  Note that the table is not a screen shot, but as a reference to verify the port mappings.

.. list-table::
    :widths: 40 40
    :header-rows: 1

    * - **Microservice**
      - **Port**
    * - Main App
      - 30511
    * - Back End
      - 31584
    * - App2
      - 30362
    * - App3
      - 31662

|image1.4.3|

.. |image1.4.1| image:: /_static/image001-4-1.png
.. |image1.4.2| image:: /_static/image001-4-2.png
.. |image1.4.3| image:: /_static/image001-4-3.png
