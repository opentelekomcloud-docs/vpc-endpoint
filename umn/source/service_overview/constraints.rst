:original_name: vpcep_01_0005.html

.. _vpcep_01_0005:

Constraints
===========

Constraints on Resource Quotas
------------------------------

:ref:`Table 1 <vpcep_01_0005__table202321419164>` describes constraints on the VPCEP resource quota.

.. _vpcep_01_0005__table202321419164:

.. table:: **Table 1** VPCEP resource quotas

   ================================= ===== =============================
   Resource                          Quota How to Increase Quota
   ================================= ===== =============================
   VPC endpoint services per account 20    :ref:`Quotas <vpcep_03_0500>`
   VPC endpoints per account         50
   ================================= ===== =============================

Other Constraints
-----------------

-  When you create a VPC endpoint, ensure that the associated VPC endpoint service has been created and is in the same region as the VPC endpoint.
-  One VPC endpoint can be used to connect to only one VPC endpoint service.
-  A VPC endpoint supports a maximum of 3,000 concurrent requests.
-  One VPC endpoint service can be connected by multiple VPC endpoints.
-  One VPC endpoint service corresponds to only one backend resource.
