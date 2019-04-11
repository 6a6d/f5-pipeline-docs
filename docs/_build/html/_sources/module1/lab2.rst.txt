BIG-IP Configuration with DO
=============================


Using the tool of your choice (i.e. VS Code, Postman, GitLab Web IDE + pipeline) configure the BIG-IP using the previously created service definition.

#. Send definition to the BIG-IP.
    #. ```POST https://{{bigip_mgmt}}/mgmt/shared/declarative-onboarding```
#. Repeat the above steps to configure the additional BIG-IPs as outlined below.

=======   ===============  =========  =============
BIG-IP    Host Name        Modules    Banner Color
=======   ===============  =========  =============
LTM1      ltm1.lab.local   ltm        red
LTM2      ltm2.lab.local   ltm        blue
GMT       gtm.lab.local    gtm        green
=======   ===============  =========  =============

#. Log into each BIG-IP and validate that configurations.

.. Note:: To reconfigure the BIG-IP, modify the DO service definition and re-post to the DO URI.
