Direct to BIG-IP AS3 Service Deployments
========================================


Deploy the AS3 Service Definition
---------------------------------
Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

#. Send the newly created definition to the BIG-IP.

    * ``POST https://{{big_ip_mgmt}}/mgmt/shared/appsvcs/declare``

#. **DO NOT** log into the BIG-IP to validate the configuration...that would be `cheating <https://youtu.be/a1Y73sPHKxw>`_.

#. Note the response back from the BIG-IP.

    - If the declaration was successful, you will receive a 200 OK response.
    - If you recieve a 4xx response back, note the error in the body and address the issue as required.

#. After successfully deploying the application, we will begin to monitor the health of the application with BIG-IQ and Graphite.


.. TODO:: Include examples of good/bad responses?


.. code-block:: json
    ::caption:: Successful Deployment

    {
        "results": [
            {
                "message": "success",
                "lineCount": 26,
                "code": 200,
                "host": "localhost",
                "tenant": "MyApp",
                "runTime": 2497
            }
        ],
    ....


.. code-block:: json
    ::caption:: Failed Deployment

    {
        "code": 422,
        "errors": [
            ": propertyName \"My-App\" should match pattern \"^[A-Za-z][0-9A-Za-z_]{0,47}$\""
        ],
        "declarationFullId": "",
        "message": "declaration is invalid"
    }


.. Note:: To reconfigure the BIG-IP, modify the AS3 service definition and re-post to the AS3 URI.
