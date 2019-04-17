BIG-IQ AS3 Service Deployments
==============================


A previously deployed AS3 service definition can be re-deployed through BIG-IQ in order to create a per-applciation dashboard for that tenant.


Deploy the AS3 Service Definition
---------------------------------

#. Save a copy of the previously deployed service definition.  Change the name of the file to represent the use of BIG-IQ.  **HTTP-service-BIQ.json**

#. Modify the existing defeintion to include a BIG-IP target that BIG-IQ will send the declaration to.  An example of an included **target** stanza can be found below.

#. POST the new service definition to the BIG-IQ's application services interface.
    * ``https://{{big_iq_mgmt}}/mgmt/shared/appsvcs/declare?async=true``

#. Record the returned UUID for this application deployment in the response body.

#. A REST endpoint on BIG-IQ has been exposed to allow for the monitoring of an AS3 service deployment.

# GET the following endpoint on the BIG-IQ and append the previous deployments UUID.
    * ``https://{{big_iq_mgmt}}/mgmt/shared/appsvcs/task/{{UUID}}``


Example Target Host in BIG-IQ AS3 Definintion
---------------------------------------------

.. code-block:: json
    :name: Generic service definition for BIG-IQ

    {
        "class": "AS3",
        "action": "deploy",
        "persist": true,
        "declaration": {
            "class": "ADC",
            "schemaVersion": "3.9.0",
            "id": "{{tenant_name}}",
            "label": "{{tenant_name}} task",
            "remark": "{{tenant_name}} - {{service_name}} Service",
            "target": {
                "hostname": "{{big_ip_mgmt}}"
            },
            "{{tenant_name}}": {
    ....


.. Note:: To reconfigure the BIG-IP, modify the AS3 service definition and re-post to the AS3 URI.
