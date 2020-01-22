Lab – Verify that the attacks are being mitigated
================================================================

-  Go to Postman console and open “Post Buy Stocks XSS Attack” in Arcadia collection

|image3.3.1|

-  Validate the XSS attack in action parameter. Click Send. Request gets rejected. Note the Support ID in response

|image3.3.2|

.. Warning:: This beta build 15.1 has an issue in UDF. The asmlogd daemon is failing due to lack of threads, hence you don’t see any logs in the GUI. This only occurs in UDF at the moment. So you can use an irule to get the ASM logs, or use the REST API calls below.
.. TODO:: Verify this is still accurate and ajust warning as necessary

-  Go to Postman Collection Arcadia-REST-WAF . Open GetEventLog

|image3.3.3|

Replace the Support ID (by the one collected in step 2) in URL and Send Request. Details for blocking is available in the response.

|image3.3.4|

.. |image3.3.1| image:: /_static/image003-3-1.png
.. |image3.3.2| image:: /_static/image003-3-2.png
.. |image3.3.3| image:: /_static/image003-3-3.png
.. |image3.3.4| image:: /_static/image003-3-4.png
