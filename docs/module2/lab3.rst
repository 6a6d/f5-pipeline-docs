Configuring Global Application Availability
===========================================


Deploy the AS3 Service Definition
---------------------------------
Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

#. Send the newly created definition to the BIG-IP.
    * ``POST https://{{big_ip_mgmt}}/mgmt/shared/appsvcs/declare``
#. Log into each BIG-IP and validate that configurations.

.. Note:: To reconfigure the BIG-IP, modify the AS3 service definition and re-post to the AS3 URI.
