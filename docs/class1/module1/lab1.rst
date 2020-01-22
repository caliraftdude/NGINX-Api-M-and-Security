Lab – Reviewing the Lab Environment
================================================================

.. NOTE:: Because of the nature of a Kubernetes cluster appication and virtual environment, it is important to understand the different layers and how they are exposed.  Pay careful attention to how the services are proxied and what they are connected to.

UDF Demostration Environment
-----------------------------------
.. TODO:: Get the standard blurbs for accessing UDF.. Aaron? Paul?

|image1.1.1|

Lab Topology
-----------------------------------
.. TODO:: Get an image of the lab topology

The following components have been included in your lab environment:

- 1 x F5 BIG-IP VE (v15.1.0)
- 1 x Kubernetes Cluster
  - 1 x Master, Ubuntu 16.04 LTS
  - 2 x Nodes, Ubuntu 16.04 LTS
- 1 x NGINX Controller 3.0.0, Ubuntu 16.04 LTS
- 1 x Windows Jumphost
- 1 x Docker instance running the lab guide

|image1.1.2|

Lab Components
-----------------------------------
.. TODO:: Update/fix lab components table

The following table lists VLANS, IP Addresses and Credentials for all
components:

.. list-table::
    :widths: 20 40 40
    :header-rows: 1
    :stub-columns: 1

    * - **Component**
      - **VLAN/IP Address(es)**
      - **Credentials**
    * - Sample Host
      - - **Management:** 10.1.1.250
        - **Internal:** 10.1.10.250
        - **External:** 10.1.20.250
      - ``admin``/``admin``

Expected time to complete: **2 hours**

.. |image1.1.1| image:: /_static/image001-1-1.png

.. |image1.1.2| image:: /_static/image001-1-2.png
