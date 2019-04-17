TS Validation
=============


Using Graphite
--------------

Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

#. Send the newly created definition to the BIG-IP.
    * ```POST https://{{big_ip_mgmt}}/mgmt/shared/telemetry/declare```
#. Log into the Graphite console and validate that metrics are being sent from the BIG-IP.

.. Note:: Telemetry data may take 2-3 minutes to populate the Graphite dashboards.
