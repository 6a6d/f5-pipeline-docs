Application Services Extension (AS3)
====================================

Deploy a Simple HTTP Based Service
----------------------------------

After this exercise, your simple HTTP based service should look like the below.

#. Tenant Name: MyWebService
#. Service Name: ServiceName
#. Application Name: AppName
#. Pool: HTTP based monitor
#. Pool members:
    #. 10.1.20.11:80
    #. 10.1.20.12:80

Building the AS3 Service Definition
-----------------------------------
#. Use the below example AS3 declaration as a template for configuring a generic HTTP service.
#. Replace the REST **{{variables}}** with an appropriate value.
#. Validate the JSON payload
    - JSON linter such as `JSONLint <https://jsonlint.com/>`_
    - Native VS Code fuctionality

#. Save the configuration as it will be used later to reconfigure the service.

Example AS3 Declaration
-----------------------
Below is generic service definition for AS3.

.. code-block:: json
    :name: Generic service definition

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
                    "template": "http",
                    "ServiceMain": {
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
                                    "{{node2_ip}}"
                                ]
                            }
                        ]
                    }
                }
            }
        }
    }
