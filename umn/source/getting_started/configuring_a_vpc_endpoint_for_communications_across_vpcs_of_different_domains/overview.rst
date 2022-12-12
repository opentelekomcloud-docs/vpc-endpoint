:original_name: vpcep_02_02031.html

.. _vpcep_02_02031:

Overview
========

Scenarios
---------

With VPCEP, you can access resources across VPCs in the same region.

Cloud resources in different VPCs are isolated from each other and cannot be accessed using private IP addresses. After you create a VPC endpoint, you can use a private IP address to access resources across two VPCs despite of network isolation between them.

This section describes how cloud resources in VPCs of different domains in the same region can communicate with each other across VPCs.

VPC 1 and VPC 2 belong to different domains. You can take the ELB in VPC 2 as a VPC endpoint service and create a VPC endpoint in VPC 1 so that the ECS in VPC 1 can access the ELB in VPC 2 using the private IP address.


.. figure:: /_static/images/en-us_image_0298376151.png
   :alt: **Figure 1** Cross-VPC communications

   **Figure 1** Cross-VPC communications

.. note::

   -  Only one-way communications from the VPC endpoint to the VPC endpoint service are supported.
   -  Before you create a VPC endpoint, add the authorized domain ID of VPC 1 to the whitelist of the VPC endpoint service in VPC 2.
   -  For details about communications between two VPCs of the same domain, see :ref:`Configuring a VPC Endpoint for Communications Across VPCs of the Same Domain <vpcep_02_0200>`.

Cross-VPC Communications
------------------------

:ref:`Figure 2 <vpcep_02_02031__fig2237134915142>` shows how to enable communications between two VPCs of different domains using VPCEP.

.. _vpcep_02_02031__fig2237134915142:

.. figure:: /_static/images/en-us_image_0298556321.png
   :alt: **Figure 2** Cross-VPC communications flowchart

   **Figure 2** Cross-VPC communications flowchart
