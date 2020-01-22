Lab – Declaratively create a WAF Policy using a Swagger file
================================================================


.. Warning:: In this lab, you will NOT use the new “declarative WAF API”. You will use the already existing capability to import a Swagger file (v3 in 15.1), and then create a policy, from an API call and NOT from a declarative call. TMOS binary and documentation of the declarative WAF API was not ready in time for ISC lab building.
.. TODO:: Verify if this is necessary/appropriate and then edit this warning accordingly

-  Open Postman by clicking on shortcut or Clicking the icon on Quick launch toolbar

|image3.2.1|

-  Collection Name: Arcadia-REST-WAF. Double Click Upload Swagger

|image3.2.2|

-  Ensure proper credentials are provided

|image3.2.3|

-  Ensure the following headers are set

|image3.2.4|

-  Ensure the following body is set

|image3.2.5|

-  Locate Swagger file (swagger_arcadia.yaml) for Arcadia in Downloads folder

|image3.2.6|

-  Click Send to upload swagger file

|image3.2.7|

-  Swagger file is uploaded

|image3.2.8|

-  Validate by checking the directory /ts/var/rest. There will be a file named admin~openapi_arcadia1.yaml

|image3.2.9|

-  On the postman collection, open Postman call named “Import Swagger”. Validate authentication credentials

|image3.2.10|

-  Validate Headers

|image3.2.11|

-  Validate the Body has the following JSON. Click Send

|image3.2.12|

-  It should show the following response.

|image3.2.13|

-  Validate the status of policy creation, by running CheckImportStatus REST call

|image3.2.14|

-  On successful completion, we should see status “ COMPLETED”

|image3.2.15|

-  Open Postman REST call RetrieveASMPolicies. Click Send

|image3.2.16|

-  Find the policy from the list for arcadia_policy. Check out the link for policy, to get policy hash. This will be used in the next steps. The hash should be OlIA0JHg0YuTH1LW4KgaSw

|image3.2.17|

-  Open postman REST call AttachPolicyToVS. Ensure the URL has the correct Policy Hash. Click Send to submite Request

|image3.2.18|

-  Server returns 200 and Policy is patched

|image3.2.19|

-  Log in to BIGIP Application Security> Security Policy > Policy List. There should be a policy name arcadia_policy

|image3.2.20|

-  To block attacks, move the attack signatures from staging to blocking mode. Click arcadia_policy

-  Click on Attack Signatures

|image3.2.21|

-  Click Enforce> Enforce all Staged Signatures

|image3.2.22|

-  Click Apply Policy

|image3.2.23|

.. |image3.2.1| image:: /_static/image003-2-1.png
.. |image3.2.2| image:: /_static/image003-2-2.png
.. |image3.2.3| image:: /_static/image003-2-3.png
.. |image3.2.4| image:: /_static/image003-2-4.png
.. |image3.2.5| image:: /_static/image003-2-5.png
.. |image3.2.6| image:: /_static/image003-2-6.png
.. |image3.2.7| image:: /_static/image003-2-7.png
.. |image3.2.8| image:: /_static/image003-2-8.png
.. |image3.2.9| image:: /_static/image003-2-9.png
.. |image3.2.10| image:: /_static/image003-2-10.png
.. |image3.2.11| image:: /_static/image003-2-11.png
.. |image3.2.12| image:: /_static/image003-2-12.png
.. |image3.2.13| image:: /_static/image003-2-13.png
.. |image3.2.14| image:: /_static/image003-2-14.png
.. |image3.2.15| image:: /_static/image003-2-15.png
.. |image3.2.16| image:: /_static/image003-2-16.png
.. |image3.2.17| image:: /_static/image003-2-17.png
.. |image3.2.18| image:: /_static/image003-2-18.png
.. |image3.2.19| image:: /_static/image003-2-19.png
.. |image3.2.20| image:: /_static/image003-2-20.png
.. |image3.2.21| image:: /_static/image003-2-21.png
.. |image3.2.22| image:: /_static/image003-2-22.png
.. |image3.2.23| image:: /_static/image003-2-23.png
