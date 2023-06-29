:original_name: vpcep_04_0005.html

.. _vpcep_04_0005:

What Statuses Are Available for a VPC Endpoint Service and VPC Endpoint?
========================================================================

:ref:`Table 1 <vpcep_04_0005__table740435852615>` describes statuses of a VPC endpoint service and their meanings.

.. _vpcep_04_0005__table740435852615:

.. table:: **Table 1** Statuses of a VPC endpoint service

   +-----------+-----------------------------------------------------------------------------------+
   | Status    | Description                                                                       |
   +===========+===================================================================================+
   | Creating  | Indicates that the VPC endpoint service is being created.                         |
   +-----------+-----------------------------------------------------------------------------------+
   | Available | Indicates that the VPC endpoint service is created and can accept a VPC endpoint. |
   +-----------+-----------------------------------------------------------------------------------+
   | Failed    | Indicates that the VPC endpoint service fails to be created.                      |
   +-----------+-----------------------------------------------------------------------------------+
   | Deleting  | Indicates that the VPC endpoint service is being deleted.                         |
   +-----------+-----------------------------------------------------------------------------------+
   | Deleted   | Indicates that the VPC endpoint service has been deleted.                         |
   +-----------+-----------------------------------------------------------------------------------+

:ref:`Table 2 <vpcep_04_0005__table134332505311>` describes statuses of a VPC endpoint and their meanings.

.. _vpcep_04_0005__table134332505311:

.. table:: **Table 2** Statuses of a VPC endpoint

   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Status             | Description                                                                                                |
   +====================+============================================================================================================+
   | Pending acceptance | Indicates that the VPC endpoint is pending acceptance of the owner of the associated VPC endpoint service. |
   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Creating           | Indicates that the VPC endpoint is connecting to the associated VPC endpoint service.                      |
   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Accepted           | Indicates that the VPC endpoint is accepted by the associated VPC endpoint service.                        |
   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Rejected           | Indicates that the VPC endpoint is rejected by the associated VPC endpoint service.                        |
   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Failed             | Indicates that the VPC endpoint fails to connect to the associated VPC endpoint service.                   |
   +--------------------+------------------------------------------------------------------------------------------------------------+
   | Deleting           | Indicates that the VPC endpoint is being deleted.                                                          |
   +--------------------+------------------------------------------------------------------------------------------------------------+
