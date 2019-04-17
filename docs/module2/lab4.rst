Delete a Deployed Service
=========================

Time to Nuke!
-------------

#. Before moving forward, were going to delete the existing tenant.  This service will get redeployed in the next lab using the AS3 Container.
#. Send a DELETE to the AS3 interface.  Make sure to include a ``tenant name`` otherwise all of the existing tenants will be destroyed.
    * DELETE ``https://{{big_ip_mgmt}}/mgmt/shared/appsvcs/declare/{{tenant_name}}``
#. Verify that the proper tenant has been deleted.
