Lab – Reviewing the Arcadia applicaiton
================================================================

-  Connect to the Windows Jumpbox using RDP with the credentials provided below:

.. NOTE:: Username **user**  Password **user**

|image1.3.1|

-  Launch Chrome and click on the Arcadia Finance bookmark.

|image1.3.2|

-  Click on the Login button found on the top right corner

.. NOTE:: Username **admin**  Password **iloveblue**

|image1.3.3|

-  You are now connected to Arcadia Finance as an Arcadia **customer**.

|image1.3.4|

.. NOTE:: As you can see, the application is not quite fully deployed with two parts missing.  The Money Transfer feature at the bottom of the UI and on the right banners is not available.  At the top right corner is a "Refer Friend" feature that is also not deployed.

-  The Arcadia Finance application is spread between four microservices running in a Kubernetes cluster.  The microservices are as follows:

#.  Main app
#.  Back End DB
#.  Money Transfer    * Not deployed
#.  Refer Friend      * Not deployed

|image1.3.5|

.. |image1.3.1| image:: /_static/image001-3-1.png
.. |image1.3.2| image:: /_static/image001-3-2.png
.. |image1.3.3| image:: /_static/image001-3-3.png
.. |image1.3.4| image:: /_static/image001-3-4.png
.. |image1.3.5| image:: /_static/image001-3-5.png
