Lab Information
===============

.. Note:: All work for this lab can be performed exclusively from the Windows Jumphost.  No installation or interaction with your local system is required.  If you choose to use your location machine for lab work, please follow the instructions in the selfBuilt_ section.

Lab Topology
------------

The network topology implemented for this lab is very simple as the emphasis is placed on Control Plane programmability.

The following components have been included in your lab environment:

-  3 x BIG-IPs (v13.1.x)
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

   * - BIG-IP LTM1
     - 10.1.1.8
     - **External:** 10.1.10.8
       **Internal:** 10.1.20.8
     - ``admin/purple123``
       ``root/default``

   * - BIG-IP LTM2
     - 10.1.1.8
     - **External:** 10.1.10.8
       **Internal:** 10.1.20.8
     - ``admin/purple123``
       ``root/default``

   * - BIG-IP GTM
     - 10.1.1.5
     - **External:** 10.1.10.5
       **Internal:** 10.1.20.5
     - ``admin/purple123``
       ``root/default``

   * - BIG-IQ Console
     - 10.1.1.6
     - **External:** 10.1.10.6
       **Internal:** 10.1.20.6
     - ``admin/purple123``
       ``root/default``

   * - BIG-IQ DCD
     - 10.1.1.7
     - **External:** 10.1.10.7
       **Internal:** 10.1.20.7
     - ``admin/purple123``
       ``root/default``

   * - Linux Tool Box
     - 10.1.1.10
     - **External:** 10.1.10.10
     - ``ubuntu/ubuntu``

   * - Linux Web Server
     - 10.1.1.11
     - **Internal1:** 10.1.20.11
       **Internal2:** 10.1.20.12
       **Internal3:** 10.1.20.13
       **Internal4:** 10.1.20.14
       **Internal5:** 10.1.20.15
     - ``ubuntu/ubuntu``

   * - Windows Jumphost
     - 10.1.1.14
     - **External:** 10.1.10.240
     - ``f5demo/purple123``


.. toctree::
   :maxdepth: 1
   :glob:

   services
   udf
