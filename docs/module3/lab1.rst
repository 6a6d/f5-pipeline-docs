Telemetry Streaming (TS)
========================

Building the TS Service Definition
-----------------------------------
#. Use the below example TS declaration as a template for configuring a generic HTTP service.
#. Replace the REST **{{variables}}** with an appropriate value.
#. Validate the JSON payload using like jsonlint.com
#. Save the configuration as it will be used later to reconfigure the service.

.. Note:: The below TS definition will stream metrics from all configured tenants.

Example AS3 Declaration
-----------------------
Below is an example of a generic HTTP based service definition for AS3.

.. code-block:: rest
    :caption: POST
    :name: Generic service definition

    @bigip_mgmt = ltm1.lab.local

    ###

    POST https://{{bigip_mgmt}}/mgmt/shared/telemetry/declare
    Authorization: Basic admin admin
    Content-Type: application/json

    {
        "class": "Telemetry",
        "controls": {
            "class": "Controls",
            "logLevel": "info"
        },
        "My_Poller": {
            "class": "Telemetry_System_Poller",
            "interval": 60
        },
        "My_Consumer": {
            "class": "Telemetry_Consumer",
            "type": "Statsd",
            "host": "{{destination_host}}",
            "protocol": "udp",
            "port": "8125"
        }
    }
