Lab – Deploy JWT authorization in NGINX+
================================================================

Deploy JWT Authorization for App2

-  Create Client Group in Nginx Controller. Click Client Groups, and then click “Create a Group”

|image2.3.1|

-  Put name Arcadia Users in “Name”. In the lab, we use JWT key file, so select JWT as “Type”. Then click “browse” and select the “jwt_key_file_API.jwk”, and click “Create”.

.. Warning:: Be aware that if you use your local Laptop browser, you will browse locally your own laptop, so you will not find the file. So you can go to the WINDOWS Jumphost or use your laptop by downloading first the JWT file from this public place : https://iscfy20-lab-apim-nginx.s3-us-west-1.amazonaws.com/JWK_files/jwt_key_file_API.jwk or create the file directly.
.. TODO:: Verify that this link is still valid within this lab

.. code-block:: json

    {"keys":
        [{
            "k":"aWxvdmVuZ2lueA",
            "kty":"oct"
        }]
    }

.. seealso:: The JWK file has to be created as above. The “k” is the secret key shared between the Authorization Server and the Resource Server. The key is ilovenginx encoded in base64. The format of the key is Octet.

|image2.3.2|

-  Add JWT policy to Arcadia API. Click “API Definitions”, and click edit icon for “prod API” environment; click “Add a Policy”.

|image2.3.3|

-  Select “Authentication” in Policy Type, “Arcadia Users” in Client Group, “Bearer Token” in Credential Location jwt, and click “Save”

|image2.3.4|

-  Click Publish and verify access via Postman

-  Open Arcadia Collection, and select “Last Transactions”, in request configuration, select NoAuth for “Authorization”, and click Send. You should see “401 Unauthorized” message

|image2.3.5|

-  Select Bearer Token for “Authorization”, copy the “token user :” from file “JWT Token.txt” (located in Downloads folder in Windows Jumphost), paste it in “Token” (one previous token can already exist, overwrite it), and Click on Preview Request (this add a new Autorization header in the request), then click “Send”, you will see the successful transaction.

|image2.3.6|

-  Go back to API Definition > Arcadia API > edit “Prod API” environment. Create an Access Policy by clicking the drop down icon for any resource, and select “Create new Policy”.

.. Note:: Known bug. You can not delete the access policy, only create and edit access policy is allowed in this build.
.. TODO:: Verify if this bug is still there for 3.0.0

|image2.3.7|

.. Note:: This policy will check if the JWT token contains a claim name “Role” with capital “R”, and if the value equals to “admin”

|image2.3.8|

-  Click Publish, and wait for publishing to complete

- Create 2 new resources (new API) in order to buy and sell stocks. Go back to API Definitions and edit Arcadia API Definition. Add /trading/rest/buy_stocks.php and /trading/rest/sell_stocks.php

.. Note:: As these URLs are explicit, don’t use Prefix(*) but Exact(=)

|image2.3.9|

-  Then, add routes for /trading/rest/buy_stocks.php and /trading/rest/sell_stocks.php into the “prod API” environment. Assign Allow to /trading/transactions.php and /trading/rest/sell_stocks.php, assign allow_admin to /trading/rest/buy_stocks.php.

-  Create the policy as screenshot below. Only Buy_Stocks will request JWT claim “admin”.

|image2.3.10|

-  Click Publish, and wait for publishing to complete.

-  Verify access policy via Postman

-  Open Arcadia Collection, select “Buy Stocks”. In request configuration, select Bearer Token for “Authorization”, copy the user token from file “JWT Token.txt” (still located in Downloads folder), paste it in “Token”, click “Preview Request”, and click Send. You should see “403 Forbidden” message.

|image2.3.11|

-  Copy the admin token from file “JWT Token.txt”, paste it in “Token”, click “Preview Request”, and click Send. You should see transaction successful message.

|image2.3.12|

-  Select “Sell Stocks” in collection. In request configuration, select Bearer Token for “Authorization”, copy the user token from file “JWT Token.txt”, paste it in “Token”, click “Preview Request”, and click Send. You should see successful message.

|image2.3.13|

.. Note:: Go back to the WebApp application in Chrome, refresh the page and you will see new transactions in the main app.

-  Check the JWT tokens in https://jwt.io in order to understand why user token can’t get an access.

|image2.3.14|

.. seealso:: As you defined an Access Policy to control the claim Role, only value “admin” can access to Buy_stock. Users have a “user” Role value.

.. |image2.3.1| image:: /_static/image002-3-1.png
.. |image2.3.2| image:: /_static/image002-3-2.png
.. |image2.3.3| image:: /_static/image002-3-3.png
.. |image2.3.4| image:: /_static/image002-3-4.png
.. |image2.3.5| image:: /_static/image002-3-5.png
.. |image2.3.6| image:: /_static/image002-3-6.png
.. |image2.3.7| image:: /_static/image002-3-7.png
.. |image2.3.8| image:: /_static/image002-3-8.png
.. |image2.3.9| image:: /_static/image002-3-9.png
.. |image2.3.10| image:: /_static/image002-3-10.png
.. |image2.3.11| image:: /_static/image002-3-11.png
.. |image2.3.12| image:: /_static/image002-3-12.png
.. |image2.3.13| image:: /_static/image002-3-13.png
.. |image2.3.14| image:: /_static/image002-3-14.png
