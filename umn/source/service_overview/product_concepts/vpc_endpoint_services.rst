:original_name: vpcep_01_0013.html

.. _vpcep_01_0013:

VPC Endpoint Services
=====================

A VPC endpoint service is a cloud service or a private service that can be accessed through a VPC endpoint.

There are two types of VPC endpoint services: gateway and interface.

-  Gateway VPC endpoint services are created only for cloud services.
-  Interface VPC endpoint services can be created for both cloud services and your private services. All VPC endpoint services for cloud services are created by default while those for private services need to be created by users themselves.

Gateway VPC Endpoint Services
-----------------------------

Gateway VPC endpoint services are configured from cloud services by the system. You do not have the permissions to configure such VPC endpoint services but can select them when creating a VPC endpoint.

.. note::

   Supported cloud services vary in different regions. For details, see the services that can be configured on the management console.

.. table:: **Table 1** Supported gateway VPC endpoint services

   +----------------------+---------------+-------------+-----------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | VPC Endpoint Service | Category      | Type        | Example                                 | Description                                                                                                      |
   +======================+===============+=============+=========================================+==================================================================================================================+
   | OBS                  | Cloud service | Gateway     | -  eu-de:                               | -  Select the endpoint service ending with **obs** if you want to access OBS using its private address.          |
   |                      |               |             |                                         | -  Select the endpoint service ending with **obs-internet** if you want to access OBS using its private address. |
   |                      |               |             |    com.t-systems.otc.eu-de.obs          |                                                                                                                  |
   |                      |               |             |                                         |                                                                                                                  |
   |                      |               |             | -  eu-nl:                               |                                                                                                                  |
   |                      |               |             |                                         |                                                                                                                  |
   |                      |               |             |    com.t-systems.otc.eu-nl.obs          |                                                                                                                  |
   |                      |               |             |                                         |                                                                                                                  |
   |                      |               |             |    com.t-systems.otc.eu-nl.obs-internet |                                                                                                                  |
   +----------------------+---------------+-------------+-----------------------------------------+------------------------------------------------------------------------------------------------------------------+

Interface VPC Endpoint Services
-------------------------------

Interface VPC endpoint services are mainly configured from:

-  Cloud services. You do not have the permissions to configure such VPC endpoint services but can select them when creating a VPC endpoint.
-  Your private services

.. note::

   Supported cloud services vary in different regions. For details, see the services that can be configured on the management console.

.. _vpcep_01_0013__table142624462110:

.. table:: **Table 2** Supported interface VPC endpoint services

   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPC Endpoint Service | Category               | Type        | Example                        | Description                                                                                                                                              |
   +======================+========================+=============+================================+==========================================================================================================================================================+
   | DNS                  | Cloud service          | Interface   | -  eu-de:                      | Select the endpoint service ending with **dns** if you want to access DNS over private networks.                                                         |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |    com.t-systems.otc.eu-de.dns |                                                                                                                                                          |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             | -  eu-nl:                      |                                                                                                                                                          |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |    com.t-systems.otc.eu-nl.dns |                                                                                                                                                          |
   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Load balancer        | Users' private service | Interface   | None                           | Select a load balancer as the backend resource if your services receive high traffic and demand high reliability and disaster recovery (DR) performance. |
   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ECS                  | Users' private service | Interface   | None                           | VPC endpoint services work as servers.                                                                                                                   |
   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | BMS                  | Users' private service | Interface   | None                           | VPC endpoint services work as servers.                                                                                                                   |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |                                | .. note::                                                                                                                                                |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |                                |    The BMS type will be discarded. The ELB type is recommended.                                                                                          |
   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VIP                  | Users' private service | Interface   | None                           | Backend resources of this type serve as virtual IP addresses.                                                                                            |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |                                | .. note::                                                                                                                                                |
   |                      |                        |             |                                |                                                                                                                                                          |
   |                      |                        |             |                                |    The VIP type will be discarded. The ELB type is recommended.                                                                                          |
   +----------------------+------------------------+-------------+--------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
