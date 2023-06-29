:original_name: vpcep_02_02021.html

.. _vpcep_02_02021:

Overview
========

Scenarios
---------

With VPCEP, you can access resources across VPCs in the same region.

Cloud resources in different VPCs are isolated from each other and cannot be accessed using private IP addresses. After you create a VPC endpoint, you can use a private IP address to access resources across two VPCs despite of network isolation between them.

This section describes how cloud resources in VPCs of the same domain in the same region can communicate with each other.

VPC 1 and VPC 2 belong to the same domain in the same region. You can configure ELB in VPC 2 as a VPC endpoint service and create a VPC endpoint in VPC 1. Then the ECS in VPC 1 can access ELB in VPC 2 using the private IP address.


.. figure:: /_static/images/en-us_image_0298376151.png
   :alt: **Figure 1** Cross-VPC communications

   **Figure 1** Cross-VPC communications

.. note::

   -  Only one-way communications from the VPC endpoint to the VPC endpoint service are supported.
   -  For details about communications between two VPCs of different domains, see :ref:`Configuring a VPC Endpoint for Communications Across VPCs of Different Domains <vpcep_02_0203>`.

Configuration Process
---------------------

:ref:`Figure 2 <vpcep_02_02021__fig43271246205814>` shows how to enable communications between VPCs of the same domain using VPCEP.

.. _vpcep_02_02021__fig43271246205814:

.. figure:: /_static/images/en-us_image_0298539810.png
   :alt: **Figure 2** Cross-VPC communications

   **Figure 2** Cross-VPC communications
