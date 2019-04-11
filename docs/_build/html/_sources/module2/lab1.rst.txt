Application Services Extension (AS3)
====================================


.. TODO:: Include DO references and graphics as necessary


Building the AS3 Service Definition
-----------------------------------
#. Use the below example AS3 declaration as a template for configuring a generic HTTP service.
#. Replace the REST **{{variables}}** with an appropriate value.
#. Validate the JSON payload using like jsonlint.com
#. Save the configuration as it will be used later to reconfigure the service.


Example AS3 Declaration
-----------------------
Below is an example of a generic HTTP based service definition for AS3.

.. code-block:: rest
    :caption: POST
    :name: Generic service definition

    @bigip_mgmt = ltm1.lab.local

    ###

    POST https://{{bigip_mgmt}}/mgmt/shared/declarative-onboarding
    Authorization: Basic admin admin
    Content-Type: application/json

    {
        "class": "AS3",
        "action": "deploy",
        "declaration": {
            "class": "ADC",
            "schemaVersion": "3.9.0",
            "id": "container",
            "label": "Generic TCP Service",
            "remark": "Simple TCP based service",
            "{{tenant_name}}_tenant": {
                "class": "Tenant",
                "{{service_name}}_app": {
                    "class": "Application",
                    "template": "generic",
                    "{{service_name}}_service": {
                        "class": "Service_TCP",
                        "virtualAddresses": [
                            "{{vip}}"
                        ],
                        "virtualPort": {{virtual_port}},
                        "pool": "{{service_name}}_pool"
                    },
                    "{{service_name}}_pool": {
                        "class": "Pool",
                        "monitors": [
                            "tcp"
                        ],
                        "members": [
                            {
                                "servicePort": {{virtual_port}},
                                "serverAddresses": [
                                    "{{node1_ip}}",
                                    "{{node2_ip}}",
                                ]
                            }
                        ]
                    }
                }
            }
        }
    }
