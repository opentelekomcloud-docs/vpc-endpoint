:original_name: vpcep_01_0005.html

.. _vpcep_01_0005:

Notes and Constraints
=====================

Resource Quotas
---------------

:ref:`Table 1 <vpcep_01_0005__table202321419164>` describes quotas and constraints on VPC Endpoint resources.

.. _vpcep_01_0005__table202321419164:

.. table:: **Table 1** VPC Endpoint resource quotas and constraints

   +-------------------------------------------------+-------------------------------+-------------------------------+
   | Resource                                        | Default Quota and Constraints | How to Increase Quota         |
   +=================================================+===============================+===============================+
   | VPC endpoint services per account in one region | 20                            | :ref:`Quotas <vpcep_03_0500>` |
   +-------------------------------------------------+-------------------------------+-------------------------------+
   | VPC endpoints per account in one region         | 50                            | :ref:`Quotas <vpcep_03_0500>` |
   +-------------------------------------------------+-------------------------------+-------------------------------+

Other Constraints
-----------------

-  When you create a VPC endpoint, ensure that the associated VPC endpoint service is deployed in the same region as the VPC endpoint.
-  One VPC endpoint can connect to only one VPC endpoint service.
-  A VPC endpoint supports a maximum of 3,000 concurrent connections.
-  One VPC endpoint service can be connected by multiple VPC endpoints.
-  One VPC endpoint service can have only one backend resource.
