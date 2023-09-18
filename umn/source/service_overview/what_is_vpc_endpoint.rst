:original_name: en-us_topic_0131645194.html

.. _en-us_topic_0131645194:

What Is VPC Endpoint?
=====================

VPC Endpoint (VPCEP) is a cloud service that provides secure and private channels to connect your VPCs to VPC endpoint services, including cloud services or your private services. It allows you to plan networks flexibly without having to use EIPs.

Architecture
------------

There are two types of resources: VPC endpoint services and VPC endpoints.

-  VPC endpoint services are cloud services or private services that you manually configure in VPCEP. You can access these endpoint services using VPC endpoints.

   For more information, see :ref:`VPC Endpoint Services <vpcep_01_0013>`.

-  VPC endpoints are secure and private channels for connecting VPCs to VPC endpoint services.

   For more information, see :ref:`VPC Endpoints <vpcep_01_0006>`.

.. _en-us_topic_0131645194__fig9414746114011:

.. figure:: /_static/images/en-us_image_0298978917.png
   :alt: **Figure 1** How VPCEP works

   **Figure 1** How VPCEP works

:ref:`Figure 1 <en-us_topic_0131645194__fig9414746114011>` shows the process of establishing channels for network communications between:

-  VPC 1 (ECS 1) and VPC 3 (ECS 3)
-  VPC 2 (ECS 2) and cloud services such as OBS and DNS
-  IDC and VPC 2 over VPN or Direct Connect to finally access a cloud service such as OBS or DNS

For more information, see :ref:`Application Scenarios <en-us_topic_0131645196>`.

Accessing VPCEP
---------------

A web-based console and HTTPS APIs are provided for you to access VPCEP.

-  Web-based console

   You can access VPCEP using the web-based console.

   Upon a quick configuration on the management console, you can start using VPCEP.

-  APIs

   Use this method if you need to integrate VPCEP into a third-party system for secondary development. For details, see `VPC Endpoint API Reference <https://docs.otc.t-systems.com/en-us/api/vpcep/vpcep_05_0000.html>`__.
