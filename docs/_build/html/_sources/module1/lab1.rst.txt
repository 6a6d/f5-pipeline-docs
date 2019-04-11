Declarative Onboarding
======================


.. TODO:: Include DO refernces and graphics as necessary


Initial BIG-IP Configurations
-----------------------------
Currently, the BIG-IPs (LTM 1, LTM 2 and GTM) are not licensed and have just a single interface configured.

Please referance the Lab Topology above and ensure the BIG-IPs are configured accordingly.

Using your favorite editor (i.e. VS Code), build a body to send to the Declarative Onboarding API request.

Each BIG-IP should have a seperate onboarding definition and these should be commited back into the repo to store the configuration-as-code.

You will need to configure the below items on each BIG-IP.

#. NTP Server
#. DNS Server
#. User name and password
#. BIG-IP banner

You *WILL NOT* have license or configure the self-IPs/VLANs for the BIG-IPs.


DO Configuration Requirements
-----------------------------

The BIG-IPs in this lab environment have already been configured with VLANs, self-ips, and licenses.  The below configuration items have not been configured on each BIG-IP and will need to be prior to continuing with the lab.


Building the DO Configuration
-----------------------------
Using the tool of your choice (i.e. VS Code, VIM, Postman, GitLab Web IDE) create a DO Service Definition that includes the above requirements.

#. Use the below example DO declaration as a template for configuring the BIG-IP.
#. Replace the REST **{{variables}}** with the appropriate value.  Use the below standard values in your definition for each BIG-IP as these will not change between device.
    * NTP Server: time.apple.com
    * DNS Server: 8.8.8.8
    * Timezone: CST
#. Validate the JSON payload using like jsonlint.com
#. Save the configuration before moving forward to Lab 2.


Example Onboarding Declaration
------------------------------

Below is an example onboarding definition.  In this example, the definition has been built to be used with VS Code's REST Client and deployed directly via the editor.

.. code-block:: rest
    :name: Onboarding Definition

    @bigip_mgmt = ltm1.lab.local

    ###

    POST https://{{bigip_mgmt}}/mgmt/shared/declarative-onboarding
    Authorization: Basic admin admin
    Content-Type: application/json
    {
        "declaration": {
            "schemaVersion": "1.0.0",
            "class": "Device",
            "label": "BIG-IP LTM",
            "Common": {
                "class": "Tenant",
                "hostname": "{{hostname}}",
                "dbvars": {
                    "class": "DbVariables",
                    "ui.advisory.enabled": false,
                    "ui.advisory.color": "green",
                    "ui.advisory.text": "/Common/hostname"
                },
                "myDns": {
                    "class": "DNS",
                    "nameServers": [
                        "{{dns_server}}"
                    ],
                    "search": [
                        "lab.local"
                    ]
                },
                "myNtp": {
                    "class": "NTP",
                    "servers": [
                        "{{ntp_server}}"
                    ],
                    "timezone": "{{timezone}}"
                },
                "myProvisioning": {
                    "class": "Provision",
                    "ltm": "nominal"
                }
                "dbvars": {
                    "class": "DbVariables",
                    "ui.advisory.enabled": true,
                    "ui.advisory.color": "{{color}}",
                    "ui.advisory.text": "/Common/hostname"
                }
            }
        }
    }
