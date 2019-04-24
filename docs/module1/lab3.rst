Using the DO Container and BIG-IP
==================================

Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

The definition will be sent to the DO container and then directed at a target BIG-IP for deployment.  In order to accomplish this, a ```targetHost``` must be defined in the service definition.

.. Note:: The DO container does not require Authorization to be set in the header.

.. code-block:: rest
    :name: Onboarding Definition

    {
        "class": "DO",
        "targetHost": "{{big-ip}}",
        "targetPort": {{port}},
        "targetUsername": "admin",
        "targetPassphrase": "admin",
        "declaration": {
            "class": "Device",
            "schemaVersion": "1.0.0",
            ....

1. Modify the DO definitions previously sent to each BIG-IP with changes outlined below

    - ``POST https://{{bigip_mgmt}}/mgmt/shared/declarative-onboarding``

2. Repeat the above steps to configure the additional BIG-IPs as outlined below.
3. Log into each BIG-IP and validate that configurations.

=======   ===============  ==============  =============
BIG-IP    Host Name        Modules         Banner Color
=======   ===============  ==============  =============
LTM1      ltm1.lab.local   ltm, afm, asm   blue
LTM2      ltm2.lab.local   ltm, afm, asm   yellow
GTM       gtm.lab.local    gtm             red
=======   ===============  ==============  =============

.. Note:: If successfully submitted to the DO container you will get a 202 Accepted back.

.. code-block:: json
    :name: Onboarding Definition

    {
        "result": {
            "class": "Result",
            "code": 202,
            "status": "RUNNING",
            "message": "processing",
            "errors": []
        },
        ....
    }

