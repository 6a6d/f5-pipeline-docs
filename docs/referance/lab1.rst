F5 API Authentication
=====================

For reference, the authentication URIs for both BIG-IP and BIG-IQ are included below.

.. TODO:: Include curl example

BIG-IP API Authentication
-------------------------

.. code-block:: rest
    :name: API auth url

    https://{{big_ip_mgmt}}/mgmt/shared/authn/login

.. code-block:: json
    :name: API auth payload

    {
        "username": "admin",
        "password": "admin",
        "loginProviderName": "tmos"
    }

BIG-IQ API Authentication
-------------------------

.. code-block:: rest
    :name: API auth url

    https://{{big_iq_mgmt}}/mgmt/shared/authn/login


.. code-block:: json
    :name: API auth payload

    {
        "username": "admin",
        "password": "admin",
        "loginProviderName": "tmos"
    }
