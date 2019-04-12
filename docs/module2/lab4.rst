Service Definition Deployments with AS3 Container
=================================================


Deploy the AS3 Service Definition
---------------------------------

#. Save a copy of the previously deployed service definition.  Change the name of the file to represent the use of the AS3 container.  **HTTP-service-docker.json**

#. Modify the existing defeintion to include a BIG-IP target that AS3 container will use as a target for the declaration.  An example of an included **target** stanza can be found below.

#. POST the new service definition to the BIG-IQ's application services interface.
    * ``https://{{as3_container}}/mgmt/shared/appsvcs/declare``

.. Note:: The ensure that you also include a valid user name and password in the JSON body.


Example Target Host in AS3 Container Definintion
------------------------------------------------

.. code-block:: json
    :name: Generic service definition for BIG-IQ

    {
        "class": "AS3",
        "action": "deploy",
        "targetHost": "{{big_ip_mgmt}}",
        "targetUsername": "admin",
        "targetPassphrase": "admin",
        "persist": true,
        "declaration": {
    ....
