.. _selfBuilt:

Self-Built Environment
======================

.. TODO:: Review for accuracy

.. NOTE:: Due to the variability of self-built environments your milage may vary.

If you are building your own lab environment please complete the following
steps and pre-requisites first:

#. Your network configuration matches or is similar to the topology in the :ref:`lab-topology`

#. Ensure your BIG-IP devices are licensed and have at least the following modules
   provisioned:

   - LTM
   - GMT

#. Your Tool Box server can be built two ways

   #. Build or reuse your own instance.  If should have the following services
      installed and running:

      - HTTP Server - TCP/80
      - DNS Server - UDP/53

   #. Use our server image build script located at the url below to configure
      an Ubuntu 16.04 base installation automatically.

      .. NOTE:: Please ensure that HTTP & DNS services are not installed on the
         base image

	   :raw_github_url:`/lab_environments/AWS/snops_server_setup.sh`

#. Your host should have the following applications installed:

   - Postman (v7.x)- https://getpostman.com
   - Google Chrome - https://google.com/chrome
   - VS Code - https://code.visualstudio.com/download

#. You will need to install several Postman Collections and an Environment before proceeding with the lab.

   #. Open Postman

   #. Click the 'Import' button

   #. Select 'Import from Link'

   #. Enter the following URL in the field ``https://raw.githubusercontent.com/6a6d/f5-pipeline/master/postman/F5_AS3.json``

   #. Click the 'Import' button

   #. Repeat the import process for the additional collections and the environment found below
        #. ``https://raw.githubusercontent.com/6a6d/f5-pipeline/master/postman/F5_DO.json``
        #. ``https://raw.githubusercontent.com/6a6d/f5-pipeline/master/postman/F5_TS.json``
        #. ``https://raw.githubusercontent.com/6a6d/f5-pipeline/master/postman/Auth.json``
        #. ``https://raw.githubusercontent.com/6a6d/f5-pipeline/master/postman/_F5-pipeline-env.json``

