:original_name: en-us_topic_0131645196.html

.. _en-us_topic_0131645196:

Application Scenarios
=====================

VPCEP establishes a secure and private channel between a VPC endpoint (cloud resources in a VPC) and a VPC endpoint service in the same region.

You can use VPCEP in different scenarios.

High-Speed Access to Cloud Services
-----------------------------------

After you connect an IDC to a VPC using VPN or Direct Connect, you can use a VPC endpoint to connect the VPC to a cloud service or one of your private services, so that the IDC can access the cloud service or private service.

.. _en-us_topic_0131645196__fig08596281506:

.. figure:: /_static/images/en-us_image_0298368446.png
   :alt: **Figure 1** Access to cloud services

   **Figure 1** Access to cloud services

:ref:`Figure 1 <en-us_topic_0131645196__fig08596281506>` shows the process of connecting an IDC to VPC 1 over VPN or Direct Connect, for the purposes of:

-  Accessing OBS or DNS using VPC endpoint 1
-  Accessing ECS 1 in the same VPC using VPC endpoint 2
-  Accessing ECS 2 in VPC 2 using VPC endpoint 3

For cloud migration, VPCEP has the following advantages:

-  Simple and efficient

   The IDC is directly connected to the VPC endpoint service over a private network, reducing access latency and improving efficiency.

-  Low cost

   With VPCEP, your IDC can access cloud resources over a private network, reducing your costs on public resources.

For details, see :ref:`Configuring a VPC Endpoint for Accessing the Private IP Address of OBS over Private Networks <vpcep_02_0300>`.

Cross-VPC Connection
--------------------

With VPCEP, resources in two different VPCs can communicate with each other despite of logic isolation between them as long as the two VPCs are in the same region.

.. note::

   VPC endpoints and VPC peering connections are different in security, communications methods, route configurations, and more.

   For details, see :ref:`What Are the Differences Between VPC Endpoints and VPC Peering Connections? <vpcep_04_0004>`.

.. _en-us_topic_0131645196__fig16677101915123:

.. figure:: /_static/images/en-us_image_0298376151.png
   :alt: **Figure 2** Cross-VPC connection

   **Figure 2** Cross-VPC connection

An ECS in VPC 1 uses a VPC endpoint to access a load balancer in VPC 2 over a private network. :ref:`Figure 2 <en-us_topic_0131645196__fig16677101915123>` shows the connection process.

VPCEP has the following advantages:

-  High performance

   Each gateway supports up to 1 million concurrent connections.

-  Simplified operations

   VPCEP resources can be created within seconds and take effect quickly.

For details, see the following sections:

-  :ref:`Configuring a VPC Endpoint for Communications Across VPCs of the Same Domain <vpcep_02_0200>`
-  :ref:`Configuring a VPC Endpoint for Communications Across VPCs of Different Domains <vpcep_02_0203>`
