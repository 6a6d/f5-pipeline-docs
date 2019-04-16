Lab Information
===============

.. Warning:: All work for this lab will be performed exclusively from the Jumphost.  No installation or interaction with your local system is required.

Lab Topology
------------

The network topology implemented for this lab is very simple as the emphasis is placed on Control Plane programmability.

The following components have been included in your lab environment:

-  2 x BIG-IPs (v13.1.x)
-  1 x Linux Tool Box
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

   * - Windows Jumphost
     - 10.1.1.14
     - ``external_user/password``

   * - BIG-IP GTM
     - 10.1.1.5
     - **External:** 10.1.10.5
       **Internal:** 10.1.20.5
     - ``admin/admin``
       ``root/default``

   * - BIG-IP LTM
     - 10.1.1.4
     - **External:** 10.1.10.4
       **Internal:** 10.1.20.4
     - ``admin/admin``
       ``root/default``

   * - BIG-IQ
     - 10.1.1.6
     - **External:** 10.1.10.6
       **Internal:** 10.1.20.6
     - ``admin/admin``
       ``root/default``
       
   * - Linux Tool Box
     - 10.1.1.10
     - **External:** 10.1.10.10
     - ``ubuntu/ubuntu``

   * - Linux Web Server
     - 10.1.1.11
     - **Internal1:** 10.1.20.11
     - **Internal2:** 10.1.20.12
     - **Internal3:** 10.1.20.13
     - **Internal4:** 10.1.20.14
     - **Internal5:** 10.1.20.15
     
     - ``ubuntu/ubuntu``

.. toctree::
   :maxdepth: 2
   :glob:
