Lab Information
===============

.. Note:: All work for this lab will be performed exclusively from the Jumphost.  No installation or interaction with your local system is required.  If you choose to use your location machine for lab work, please follow the instructions in the selfBuilt_ section.

Lab Topology
------------

The network topology implemented for this lab is very simple as the emphasis is placed on Control Plane programmability.

The following components have been included in your lab environment:

-  2 x BIG-IPs (v13.1.x)
-  1 x BIG-IQ (v6.1)
-  1 x BIG-IQ DCD
-  1 x Linux Tool Box
-  1 x Linux Web Server
-  1 x Windows Jumphost

.. nwdiag:: labtopology.diag
   :width: 800
   :name: lab-topology-diagram
   :scale: 110%

Network Addressing
------------------

The following table lists VLANS, IP Addresses and Credentials for all
components:

.. list-table::
   :widths: 15 30 30 30
   :header-rows: 1
   :stub-columns: 1

   * - **Component**
     - **Management IP**
     - **VLAN/IP Address(es)**
     - **Credentials**

   * - BIG-IP LTM
     - 10.1.1.4
     - **Internal:** 10.1.20.4
       **External:** 10.1.10.4
     - ``admin/admin``
       ``root/default``

   * - BIG-IP GTM
     - 10.1.1.5
     - **Internal:** 10.1.20.5
       **External:** 10.1.10.5
     - ``admin/admin``
       ``root/default``

   * - BIG-IQ Console
     - 10.1.1.6
     - **Internal:** 10.1.20.6
       **External:** 10.1.10.6
     - ``admin/admin``
       ``root/default``

   * - BIG-IQ DCD
     - 10.1.1.7
     - **Internal:** 10.1.20.7
       **External:** 10.1.10.7
     - ``admin/admin``
       ``root/default``

   * - Linux Tool Box
     - 10.1.1.10
     - **External:** 10.1.10.10
     - ``ubuntu/ubuntu``

   * - Linux Web Server
     - 10.1.1.15
     - **Internal:** 10.1.20.15
     - ``ubuntu/ubuntu``

   * - Windows Jumphost
     - 10.1.1.250
     - **External:** 10.1.10.250
     - ``f5demo/purple123``


.. toctree::
   :maxdepth: 2
   :glob:
