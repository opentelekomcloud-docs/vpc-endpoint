:original_name: vpcep_04_0004.html

.. _vpcep_04_0004:

What Are the Differences Between VPC Endpoints and VPC Peering Connections?
===========================================================================

:ref:`Table 1 <vpcep_04_0004__table485816268157>` describes differences between VPC endpoints and VPC peering connections.

.. note::

   VPC endpoints and VPC peering connections are two different resources. You can configure either of them based on your connectivity needs.

.. _vpcep_04_0004__table485816268157:

.. table:: **Table 1** Differences

   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Category                        | VPC Peering Connection                                                                                                                            | VPC Endpoint                                                                                                                                                     |
   +=================================+===================================================================================================================================================+==================================================================================================================================================================+
   | Security                        | All resources in a VPC, such as ECSs and load balancers, can be accessed.                                                                         | Allows access to a specific service or application. Only the ECSs and load balancers in the VPC for which VPC endpoint services are created can be accessed.     |
   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | CIDR block overlap              | Not supported                                                                                                                                     | Supported                                                                                                                                                        |
   |                                 |                                                                                                                                                   |                                                                                                                                                                  |
   |                                 | If two VPCs have overlapping subnets, the VPC peering connection will not work.                                                                   | If you use a VPC endpoint to connect two VPCs, you do not have to worry about overlapping subnets.                                                               |
   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Communications mode             | VPCs connected through a peering connection can communicate with each other.                                                                      | Requests can only be initiated from a VPC endpoint to a VPC endpoint service, but not the other way around.                                                      |
   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Route configuration             | If a peering connection is established between two VPCs, add routes to the VPCs so that they can communicate with each other.                     | For two VPCs that are connected through a VPC endpoint, the route has been configured, and you do not need to configure it again.                                |
   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Access using VPN/Direct Connect | Supported                                                                                                                                         | Supported                                                                                                                                                        |
   |                                 |                                                                                                                                                   |                                                                                                                                                                  |
   |                                 | You can create a VPC Peering connection to connect your on-premises data center to a cloud service using a VPN connection or a direct connection. | You can create a VPC endpoint to connect your on-premises data center to a cloud service using a VPN connection or a direct connection over an internal network. |
   +---------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
