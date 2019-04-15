Services Information
====================

Service Topology
----------------

The following services have been included in your lab environment:

-  GitLab
-  Grafana
-  Graphite
-  AS3 Container
-  DO Container
-  Web Server
-  Traffic Generator

.. nwdiag:: servicestopology.diag
   :width: 800
   :name: services-topology-diagram
   :scale: 110%

Service Addressing and Port Assignment
--------------------------------------

The following table lists IP addresses, ports and credentials for all components:

.. list-table::
   :widths: 15 30 30 30
   :header-rows: 1
   :stub-columns: 1

   * - **Component**
     - **Management IP**
     - **VLAN/IP Address(es)**
     - **Credentials**

   * - GitLab
     - 10.1.1.10:80
       **External:** 10.1.10.10:80
     - ``f5demo/purple123``

   * - Grafana
     - 10.1.1.10:3000
       **External:** 10.1.10.10:3000
     - ``admin/purple123``

   * - Grafana
     - 10.1.1.10:8080
       **External:** 10.1.10.10:8080
     - ``root/root``

   * - AS3 Container
     - 10.1.1.10:8000
     - 10.1.1.10:8443
       **External:** 10.1.10.10:8000
       **External:** 10.1.10.10:8443

   * - DO Container
     - 10.1.1.10:8001
     - 10.1.1.10:8444
       **External:** 10.1.10.10:8001
       **External:** 10.1.10.10:8444

   * - Linux Web Server
     - 10.1.1.15:80
     - **Internal:** 10.1.20.15-20:80
     - ``ubuntu/ubuntu``

   * - Windows Jumphost
     - 10.1.1.250
     - **External:** 10.1.10.250
     - ``f5demo/purple123``


.. toctree::
   :maxdepth: 2
   :glob:
