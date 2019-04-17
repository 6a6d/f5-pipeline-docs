BIG-IP Configuration with DO
=============================

Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

1. Send definition to the BIG-IP.

- ``POST https://{{bigip_mgmt}}/mgmt/shared/declarative-onboarding``

2. Repeat the above steps to configure the additional BIG-IPs as outlined below.

=======   ===============  =========  =============
BIG-IP    Host Name        Modules    Banner Color
=======   ===============  =========  =============
LTM1      ltm1.lab.local   ltm        red
GMT       gtm.lab.local    gtm        green
=======   ===============  =========  =============

4. **DO NOT** log into the BIG-IP to validate the configuration...that would be `cheating <https://youtu.be/a1Y73sPHKxw>`_.
5. Use the declarative interface to determine the configuration of each BIG-IP.

.. Note:: To reconfigure the BIG-IP, modify the DO service definition and re-post to the DO URI.
