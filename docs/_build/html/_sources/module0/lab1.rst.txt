.. _module0:

Configuring Editor Environment
==============================


VS Code - Extensions
--------------------

When using VS Code, the following extensions will be helpful but not necessary.

* Prettify JSON
* REST Client
* Python

VS Code - Schema Validate
-------------------------

In order to leverage the native IntelliSense (code completion) capabilities within VS Code a schema file will need to be referanced in a given declaration.  Once the schema is referanced, VS Code will autocomplete keywords in real time.

Declaration Validation
----------------------

#. Launch VS Code and create a new file.  Ensure you save this file with the *.json extension.
#. Reference the schema file at the top of this file


.. code-block:: json
    :name: DO Schema Reference for IntelliSense

    {
        "$schema": "https://raw.githubusercontent.com/F5Networks/f5-declarative-onboarding/master/schema/base.schema.json",
        ...
    }


.. code-block:: json
    :name: AS3 Schema Reference for IntelliSense

    {
        "$schema": "https://raw.githubusercontent.com/F5Networks/f5-appsvcs-extension/master/dist/latest/as3-examples-3.10.0-5.collection.json",
        ...
    }


.. code-block:: json
    :name: TS Schema Reference for IntelliSense

    {
        "$schema": "https://raw.githubusercontent.com/F5Networks/f5-telemetry-streaming/master/src/nodejs/schema/base_schema.json",
        ...
    }


.. NOTE::

    There is a known issue with Pool_Member class inside the pool's member array.  This may show an error as VS Code doesn't seem to properly recognize the default value of addressDiscovery.  By filling in the value as "addressDiscovery": "static", the error goes away.

