.. _module0:

Configuring Editor Environment
==============================

.. Note:: VS Code has already been installed and configured on the Windows Jumpbox.


What is Visual Studio Code?
---------------------------

Visual Studio Code (VS Code) is a code editor redefined and optimized for building and debugging modern web and cloud applications.  Visual Studio Code is free and available on all major platforms such as Linux, macOS, and Windows.

VS Code can be customized by installing extentions that support new languages, themes, and connect to additional services (e.g. AWS or Azure).

Git it built-into Visual Studio Code which makes the platform ideal for use in a SuperNetOps/IaC environment.


VS Code - Extensions
--------------------

When using VS Code, the following extensions will be helpful but not necessary.

* Prettify JSON
* REST Client
* YAML
* Python


VS Code - Schema Validate
-------------------------

In order to leverage the native IntelliSense (code completion) capabilities within VS Code a schema file will need to be referanced in a given declaration.  Once the schema is referanced, VS Code will autocomplete keywords in real time.


Service Definition Validation
-----------------------------

When creating a JSON file, such as an AS3 Service Definition, the schema can be referanced allowing VS Code to provide code completion and validation services.

#. Open an existing Service Definition using VS Code.

#. Add one of the below references to the schema at the top of the file.

#. VS Code will not provide schema validation for the service definition.


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

