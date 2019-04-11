Telemetry Streaming (TS)
========================


Deploy the TS Service Definition
--------------------------------

Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

#. Send the newly created definition to the BIG-IP.
    * ```POST https://{{big_ip_mgmt}}/mgmt/shared/telemetry/declare```
#. Log into the Graphite console and validate that metrics are being sent from the BIG-IP.

.. TODO:: Add Graphite console pic with TS data


.. Note:: Telemetry data may take 2-3 minutes to populate the Graphite dashboards.


Reconfigure TS
--------------

To monitor a single tenant, you can modify the existing TS definition and refine the **My_Poller** configuration.

#. Referance the below TS example and change your TS definition by specifying just a single tenant to monitor.
#. Log into the Graphite console and validate that metrics are still being collected from a a single tenant.

.. Hint:: Modify the previously used  TS definition instead of creating a new one.


Example of Tenant Specific TS Declaration
-----------------------------------------
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
            "interval": 60,
            "host": "localhost",
            "port": 8100,
            "protocol": "http",
            "enable": true,
            "trace": false,
            "tag": {
                "tenant": "{{tenant_name}}",
                "application": "{{application_name}}"
            }
        },
        "My_Consumer": {
            "class": "Telemetry_Consumer",
            "type": "Statsd",
            "host": "{{destination_host}}",
            "protocol": "udp",
            "port": "8125"
        }
    }
