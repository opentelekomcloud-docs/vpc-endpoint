:original_name: vpcep_03_0204.html

.. _vpcep_03_0204:

VPC Endpoint Overview
=====================

VPC endpoints are secure and private channels for connecting VPCs to VPC endpoint services.

You can create a VPC endpoint to connect a resource in your VPC to a VPC endpoint service in another VPC of the same region.

This section describes how to create and manage a VPC endpoint.

.. table:: **Table 1** Management of VPC endpoints

   +--------------------------------------------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                                                    | Description                                                      | Constraint                                                                                                                             |
   +==============================================================+==================================================================+========================================================================================================================================+
   | :ref:`Creating a VPC Endpoint <en-us_topic_0131645189>`      | Describes how to create a VPC endpoint.                          | -  VPC endpoints are region-level resources. Select a region and project when you create such a VPC endpoint.                          |
   |                                                              |                                                                  | -  Each tenant can create a maximum of 50 VPC endpoints.                                                                               |
   |                                                              |                                                                  | -  When you create a VPC endpoint, ensure that the associated VPC endpoint service is deployed in the same region as the VPC endpoint. |
   +--------------------------------------------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Querying and Accessing a VPC Endpoint <vpcep_03_0202>` | Describes how to query the summary of a VPC endpoint.            | One VPC endpoint supports up to 3,000 concurrent connections.                                                                          |
   +--------------------------------------------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Deleting a VPC Endpoint <vpcep_03_0203>`               | Describes how to delete a VPC endpoint.                          | Deleted VPC endpoints cannot be recovered. Exercise caution when performing this operation.                                            |
   +--------------------------------------------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Managing Tags of a VPC Endpoint <vpcep_03_0206>`       | Describes how to query, add, edit, and delete VPC endpoint tags. | You can add up to 20 tags to each VPC endpoint.                                                                                        |
   +--------------------------------------------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
