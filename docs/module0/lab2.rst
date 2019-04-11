F5 API Authentication
=====================

In order to interact with the REST based API for both BIG-IP and BIG-IQ, authentication needs to occur.

Below are examples of how to authenticate against both BIG-IP and BIG-IQ using Postman and Curl.

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
