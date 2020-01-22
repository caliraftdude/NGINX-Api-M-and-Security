Lab – Add a new microservice in the API definitions
================================================================

-  To verify Upstream configuration, click “Upstream Group”, and then click edit icon for app2

|image2.2.1|

.. Note:: This App2 is a new app developed by DevOps and available on the FQDN app2.example.com and port 30362. This microservice is running in Kubernetes. Now we need to publish this new microservice on the API Gateway.

-  Add app2 to API definition. Click “API Definitions”, then click the edit icon under “Arcadia WebApp”

|image2.2.2|

.. Note:: You can notice only 2 microservices are published. The / (main App) and the /files (Back End DB)

-  Click “Add Resource”, put /api into “Path”, then click “Save”

|image2.2.3|

-  Click edit icon for “prod WebApp” in “Environment”

|image2.2.4|

-  Click “Add Route”. Select /api in “Resource”, and app2 in “Upstream Group”. Click SAVE.

|image2.2.5|

6. Click “Publish”. A publish successful message will appear at top, once publish is completed.

|image2.2.6|

7. Verify app2 is running in the Web Application. RDP into Windows Jumphost, and refresh the browser session for the application. The app2 (Quick Money Transfer) appears. Do a money transfer by selecting an account in “From”, a person in “To”, fill a number in “Amount”, and click “Transfer Now”; you will see a successful message, and the money transfer transaction will show in “Transfer history”

|image2.2.7|

.. Note:: You did you first API call from the Arcadia Web Application :) Behind the scene, when you click on Transfer Now, browser makes an API Call.

-  Repeat the same configuration for Arcadia API

-  Go back to API Definition and click on edit icon for “Arcadia API”

|image2.2.8|

.. Note:: You can notice there is only one Resource at the moment, and this resource is “explicit” with the full URI.

-  Click “Add Resource”, and put /api in “Path”, and click “Save”

|image2.2.9|

-  Click edit button for “prod API” in Environment, click “Add Route”, select /api for resource, select app2 for “Upsteam Group”, and click “Save”

|image2.2.10|

-  Click “Publish”, and wait for publishing to complete

.. Note:: With these steps, you added a new “route” for the API /api. The API and the Web Application are separated at the BIG-IP level. It is 2 different VS and 2 different Pool. That why you created 2 different API Definitions.

-  Verify API call via Postman. RDP into Windows Jumphost, launch Postman, open “Arcadia” collection, select “POST Transfer Money”. Review the body and click “Send”. You should see successful message in response.

|image2.2.11|

-  Go back to the Web Application, reload the page, and check if the transaction is shown in the Money Transfer app.

|image2.2.12|


.. |image2.2.1| image:: /_static/image002-2-1.png
.. |image2.2.2| image:: /_static/image002-2-2.png
.. |image2.2.3| image:: /_static/image002-2-3.png
.. |image2.2.4| image:: /_static/image002-2-4.png
.. |image2.2.5| image:: /_static/image002-2-5.png
.. |image2.2.6| image:: /_static/image002-2-6.png
.. |image2.2.7| image:: /_static/image002-2-7.png
.. |image2.2.8| image:: /_static/image002-2-8.png
.. |image2.2.9| image:: /_static/image002-2-9.png
.. |image2.2.10| image:: /_static/image002-2-10.png
.. |image2.2.11| image:: /_static/image002-2-11.png
.. |image2.2.12| image:: /_static/image002-2-12.png
